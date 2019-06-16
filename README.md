## Deploy
  - To deploy you need a settings file at the root of the folder. Call it `settings.json`
    content of the file should be following
    ```
      {
        "galaxy.meteor.com": {
          "env": {
            "ROOT_URL": "https://chat.solacesource.com/",
            "MONGO_URL": "mongodb+srv://solacechat:<PW>@cluster0-sfcrr.mongodb.net/test?retryWrites=true"
          }
        }
      }
    ```
    NOTE: If your development environment is OS X then remove vendor file from node_module folder of npm package `sharp`. Which is casuing issues for lots of people, you can check out about the issue and why we need to do it here https://github.com/lovell/sharp/issues/1303
    ```
    rm -rf node_modules/sharp/vendor
    ```
  - To deploy to galaxy use the following command
    ```
      DEPLOY_HOSTNAME=galaxy.meteor.com meteor deploy chat.solacesource.com --settings=settings.json --owner=solacesource
    ```
    Make sure following is correct before deploying
    * Settings file path we created in first step.
    * Have access to galaxy to deploy
