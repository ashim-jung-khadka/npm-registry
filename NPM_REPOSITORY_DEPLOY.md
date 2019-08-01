# NPM Repository Deployment

We have used Sonatype Nexus Repository Manager for local npm publish.

## Nexus Repository Manager
It provides three types of repository for npm:
1. npm (group)
2. npm (hosted)
3. npm (proxy)

### npm (hosted)
- It is the private remote repository for npm dependecies.
- It is used to push our artifacts to it.

### npm (proxy)
- It is proxy repository for NPM Repository.
- It is also use to cache from internet to repo manager

### npm (group)
- It is the combination of both npm (hosted) and npm (proxy).
- It make easy to download and publish using single end-point.
- It can collect multiple remote and hosted repos under one url

## Run Nexus Repository
Here we have used volume to share all the data related to nexus
inside `data` directory.

```shell
# It will expose the port : `8081`
docker-compose up
```

URL : http://localhost:8081
