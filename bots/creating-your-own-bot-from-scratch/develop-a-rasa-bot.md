# Develop a Rasa Bot

[Rasa](https://rasa.com/) is the leading open-source machine learning toolkit that lets developers expand bots beyond answering simple questions with minimal training data. At the core, Rasa bot has a machine learning model which trained on example conversations.

Rasa is developed with Python but for the most part, you don't need to know Python to design the basic conversational flows. You will need Python knowledge only when creating custom actions in Rasa which call external actions.

## Quick start guide

The fastest way to start with Rasa is using [Rasa starter kit](https://github.com/RocketChat/rasa-kick-starter). The starter kit uses webhooks to communicate between Rasa and Rocket.Chat.

### Get the Rasa Bot Boilerplate Code

* Navigate to the directory you want to develop your bot in and clone this boilerplate code from our repository

```
git clone https://github.com/RocketChat/rasa-kick-starter.git
cd rasa-kick-starter/
```

* To configure the bots credentials, open the `rasa-kick-starter/bot_rasa` folder and update the `credentials.yml` file with Rasa bot's username, password, and Rocket.Chat URL. See this section on how to [#1.-create-a-bot-user](./#1.-create-a-bot-user "mention")

```yaml
rocketchat:
user: "<RASA USER NAME>"
password: "<RASA USER PASS>"
server_url: "<ROCKETCHAT HOST>"
```

* Train the bot's Machine Learning Model by running&#x20;

```
docker run -it -v $(pwd)/bot_rasa:/app rasa/rasa train
```

After the training, the machine learning model will be created inside the `bot_rasa/models` folder.

* Run the bot by typing

```
docker-compose up bot_rasa
```

You should see the following output:

```
$ docker-compose up bot_rasa
Starting rasa-kick-starter_bot_rasa_1 ... done
Attaching to rasa-kick-starter_bot_rasa_1
bot_rasa_1            | 2021-11-24 21:23:24 INFO     root  - Starting Rasa server on http://localhost:5005
```

Open your browser and navigate to `http://localhost:5005`. You should see the response from the running Rasa bot:

```
Hello from Rasa: 1.5.0a1
```

If you have Rocket.Chat running on the same machine, the bot's URL is `http://bot_rasa:5005`. This guide uses a remote Rocket.Chat instance, so it is necessary to get a public URL for the Rasa bot to be able to link it properly. It is recommended to use [ngrok](https://ngrok.com/download) for this purpose.

[Download ngrok](https://ngrok.com/download), open terminal in the folder you downloaded ngrok to and execute the following command:

```
./ngrok http 5005
```

You should see the following output:

```
Session Status                online
Session Expires               7 hours, 59 minutes
Version                       2.3.35
Region                        United States (us)
Web Interface                 http://127.0.0.1:4040
Forwarding                    http://dde093e1.ngrok.io -> http://localhost:5005
Forwarding                    https://dde093e1.ngrok.io -> http://localhost:5005
```

Public URL will be provided next to `Forwarding` column. In this case, `http://dde093e1.ngrok.io`.

#### Configure RocketChat Webhook

Go to **Administration > Integrations**. Click `New Integration` button in the top right corner and then select `Outgoing WebHook`.

Select `Message Sent` Event Trigger from the dropdown list. Complete the configuration with the following settings:

* Enabled: `True`
* Channel: `#general`
* URLs: `http://<ngrok_public_url>/webhooks/rocketchat/webhook`
* Post as: `<RASA USER NAME>`

**NOTE**: Make sure you replace the URL with a valid public URL obtained on the previous step using ngrok.

When you are done, click **Save.**

![](<../../.gitbook/assets/image (65).png>)

#### Talk to your Bot

On the server, login as a regular user (not the BOT user), go to `general` room, and try to talk to your bot by typing `@bot_rasa hello`:

![Rasa bot is talking](<../../.gitbook/assets/rasa\_bot\_example (1) (1) (1) (2) (2) (2) (2) (2) (2) (2) (1) (2) (2) (2) (2) (2) (2) (2) (2) (2) (1) (1) (1) (1).png>)
