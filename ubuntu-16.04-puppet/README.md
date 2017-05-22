# ubuntu-16.04-puppet

To get the latest version of the puppet agent installed
```
docker build -t ubuntu-16.04-puppet:latest .
```

To get a specific version of the puppet agent installed
```
AGENT_VERSION="1.10.0"; docker build --build-arg AGENT_VERSION=$AGENT_VERSION
-t ubuntu-16.04-puppet:$AGENT_VERSION .
```

