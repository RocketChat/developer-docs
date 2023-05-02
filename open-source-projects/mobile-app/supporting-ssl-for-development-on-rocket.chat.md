# Supporting SSL for development on Rocket.Chat

When working with mobile apps, it is required that your server supports SSL.

Rocket.Chat is a "middle-tier application server." It does not handle SSL itself. However, Rocket.Chat works well with several industrial-grade, battle-tested reverse proxy servers you can configure to handle SSL.

Your Rocket.Chat server may be publicly accessible on the internet or not. Let's look at how to configure SSL for both scenarios.

## The Rocket.Chat server is publicly accessible on the internet

If your server is publicly accessible, it is recommended that you use a service like [Let's Encrypt](https://letsencrypt.org/) to obtain your SSL certificates.

For Ubuntu users, it can be configured automatically using [Snaps](https://docs.rocket.chat/deploy/prepare-for-your-deployment/rapid-deployment-methods/snaps).

{% hint style="info" %}
To learn more about configuring your choice of SSL Reverse proxy servers, see [Configuring SSL Reverse Proxy](https://docs.rocket.chat/deploy/rocket.chat-environment-configuration/configuring-ssl-reverse-proxy).
{% endhint %}

## The Rocket.Chat server is not accessible on the internet

If your server is not accessible on the internet, you need to provide self-signed certificates to configure SSL on the server.

To create your SSL certificates,  you must generate a self-signed root certificate. The steps highlighted below is adapted from the resource " [Self Signed Certificate with Custom Root CA](https://gist.github.com/fntlnz/cf14feb5a46b2eda428e000157447309).".

### Create Root CA

#### Create Root Key

The root key plays a crucial role in signing certificate requests. It is essential to keep it secure, as possessing it grants the ability to sign certificates on your behalf.

```
openssl genrsa -des3 -out Rocket.Chat-root.key 4096
```

{% hint style="warning" %}
If you want a non-password-protected key, remove the `-des3` option.
{% endhint %}

#### Create and self-sign the Root Certificate

Create the root certificate with the root key and distribute it to all computers that should trust you.

```
openssl req -x509 -new -nodes -key Rocket.Chat-root.key -sha256 -days 1024 -out Rocket.Chat-root.crt
```

{% hint style="info" %}
It is **not recommended** that you distribute this root certificate in production. A breach of the above-generated key will open every device that trusts your root certificate to potential security threats.
{% endhint %}

### Create an SSL certificate

#### Create the Certificate Key

```
openssl genrsa -out mydomain.com.key 2048
```

{% hint style="info" %}
Replace `mydomain.com` with your IP address. [Bonjour](https://developer.apple.com/library/content/documentation/Cocoa/Conceptual/NetServices/Articles/about.html#//apple\_ref/doc/uid/TP40002458-SW1) local domains also work!
{% endhint %}

#### Create the Certificate Signing Request

While creating the certificate signing request, it is important to specify the `Common Name` providing the IP address or URL for the service; otherwise, the certificate cannot be verified.

```
openssl req -new -key mydomain.com.key -out mydomain.com.csr
```

#### Generate the SSL certificate

Here, we are using the `mydomain.com` CSR, along with the `Rocket.Chat-root` CA.

```
openssl x509 -req -in mydomain.com.csr -CA Rocket.Chat-root.crt -CAkey Rocket.Chat-root.key -CAcreateserial -out mydomain.com.crt -days 365 -sha256
```

### Configuring SSL for Rocket.Chat

The `mydomain.com.crt` and `mydomain.com.key` files generated above are used as the certificate and the private key to configure SSL.

{% hint style="info" %}
To learn more about configuring your choice of SSL Reverse proxy servers, see [Configuring SSL Reverse Proxy](https://docs.rocket.chat/deploy/rocket.chat-environment-configuration/configuring-ssl-reverse-proxy).
{% endhint %}

### Trusting Certificate Authority

All the devices that need to communicate with the server during development need to trust the root certificate [generated earlier](supporting-ssl-for-development-on-rocket.chat.md#create-and-self-sign-the-root-certificate) (`Rocket.Chat-root.crt`).

* For Apple devices, see [Installing a CA’s Root Certificate on Your Test Device](https://developer.apple.com/library/archive/qa/qa1948/\_index.html#//apple\_ref/doc/uid/DTS40017603-CH1-SECINSTALLING).
* For Android devices, see [Add & Remove certificates](https://support.google.com/nexus/answer/2844832?hl=en).

Once the root certificate has been installed successfully, the device can access Rocket.Chat over SSL.

## Troubleshooting

If your device is not able to connect over SSL, ensure that the URL has `https://` explicitly typed out before it.
