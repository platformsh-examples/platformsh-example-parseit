#Example Parse.com Configuration for Platform.Sh

Parse are retiring their service .. and people will need to find alternate methods to host their code (while probably migrating to some other service).

Anyway,  Platform.sh has everything that is needed to run a Parse server (unlike  other providers you don't need an external service for MongoDB).

Currently mongodb is hardcoded in start command, but it's fine. Not gonna change.

Configuration:

`platform variable:set APP_ID this_is_my_app_id`
`platform variable:set MASTER_KEY this_is_my_master_key`

To test: 

```
curl -X POST \
-H "X-Parse-Application-Id: this_is_my_app_id" \
-H "Content-Type: application/json" \
-d '{"score":1337,"playerName":"Sean Plott","cheatMode":false}' \
http://master-7rqtwti-{yourproject-id}.{platform-shregion}}.platformsh.site/parse/classes/GameScore
```

You should change of course the values to match yours, most importantly the url .. `http://master-7rqtwti-{yourproject-id}.{platform-shregion}}.platformsh.site` 