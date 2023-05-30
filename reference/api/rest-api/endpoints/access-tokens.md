# Access Tokens

Using personal access tokens, the REST API can be utilized without the need for signing in.

The administrator must grant the your user role the necessary permission`create-personal-access-tokens` to be able to generate personal access tokens.

Next, navigate to **Avatar menu > My Account > Security > Personal Access Tokens** and generate personal access tokens.. Once

The tokens that will be generated are irrecoverable. Once generated, you must save them in a safe place. If the token is lost or forgotten, you can regenerate or delete the token.

With the token in hand, you can add in the header `X-Auth-Token` along with your user id `X-User-Id` of the request that is made to the REST API.
