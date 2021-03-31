This is a companion server to the [Cant Stand Still Admin](https://github.com/Noah-Silvera/cant-stand-still-admin) repository. This server will receive webhooks from strava and forward them to the admin server for processing.

## Starting Locally

1. `gem install dotenv`
1. Create a .env file locally that has the following variables
    * `STRAVA_CLIENT_ID`
    * `STRAVA_CLIENT_SECRET`
    * `CALLBACK_URL` the url that strava will callback to for webhook requests. This url **must be https**. An ngrok proxy can be used to satisfy this locally
    * `WEBHOOK_TOKEN` a unique string that will be used for verification with the strava API
1. Start the webhook server `dotenv bundle exec ruby ./server.rb handle`
2. Create the subscription `dotenv bundle exec ruby ./server.rb create`

anddd your done! The webhook server now has an active subscription and will process any webhook requests that come in from strava
