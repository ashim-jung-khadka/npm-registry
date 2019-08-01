# NPM Registry

## Registry-Publisher
Publish the project to the specified repository. It also defines
peerDependency to make contract what minimun version it uses to build
the code.
```
npm publish
```

## Registry-Consumer
Consumes the `registry-producer` dependency via private repository
and all other dependency will be downloaded from NPM public registry.
```
"dependencies": {
    ....
    "@contract/registry-producer": "^1.0.0"
  }
```

Just file `npm install` command on terminal, it will download dependency
from both private and public repository.

## Configuration
Place following content inside `package.json`.
```json
"publishConfig": {
  "registry": "http://192.168.1.66:8081/repository/npm-private/"
}
```

## Registry Config
Create new file `.npmrc` inside home directory.
Npm uses this file to download all the dependency from the repo either
public or private.

Here, we have used `ng-scope` for registry : `@contract`.

```json
@contract:registry=http://localhost:8081/repository/npm-private/
_auth="YWRtaW46YWRtaW4xMjM="
email=ashim.khadka@clusus.com
prefix=/home/ashimjk/.npm
```

## Private Registry Auth Key
It is base64 encoded key : "username:password".
```
echo -n 'admin:admin123' | openssl base64
```
