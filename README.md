# Minimalistic Example Parse.com Configuration for Platform.sh

Parse  retired their service .. and people will need to find alternate methods to host their code (while probably migrating to some other 
service).

Platform.sh has everything that is needed to run a Parse server (unlike  other providers you don't need an external service for MongoDB).

## Starting a new project

To start a new project based on this template, follow these 3 simple steps:

1. Clone this repository locally.  You may optionally remove the `origin` remote or remove the `.git` directory and re-init the project if you want a clean history.
 
2. Create a new project through the Platform.sh user interface and select "Import an existing project" when prompted.

3. Run the provided Git commands to add a Platform.sh remote and push the code to the Platform.sh repository.

That's it!  You now have a working "hello world" level project you can build on.

## Using as a reference

You can also use this repository as a reference for your own projects, and borrow whatever code is needed. The most important parts are the `.platform.app.yaml` file and the `.platform` directory.

## Configuration
Configuration (assuming you have the platform.sh CLI installed):

`platform variable:set env:APP_ID this_is_my_app_id`
`platform variable:set env:MASTER_KEY this_is_my_master_key`

To test: 

```
curl -X POST \
-H "X-Parse-Application-Id: this_is_my_app_id" \
-H "Content-Type: application/json" \
-d '{"score":1337,"playerName":"Sean Plott","cheatMode":false}' \
http://master-7rqtwti-{yourproject-id}.{platform-shregion}}.platformsh.site/parse/classes/GameScore
```

You should change of course the values to match yours, most importantly the url .. `http://master-7rqtwti-{yourproject-id}.{platform-shregion}}.platformsh.site` 
