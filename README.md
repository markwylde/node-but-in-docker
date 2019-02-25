# What is this all about?
Instead of having to install node, npm and a bunch of dependancies on your local machine for every project you have, you can run node in a sandboxed Docker container.

# How do I install it?
There's not really an install process. You simply copy the files from the bin folder in this repo into your `/usr/local/bin` folder. Then you can run `node` or `npm` as normal, but it will spin up a new docker container.

```bash
git clone https://github.com/markwylde/node-but-in-docker.git
sudo cp ./bin/* /usr/local/bin
```

# How do I use it?
You can just run node or npm from your favourite terminal on your local machine as normal. Your current working directory will be shared automatically at `/app` in the container.

There are a few caveats though:

## Exposing ports is not automatic
If you are building an app that exposes ports, then you need to tell docker to expose those ports to the local machine. You can pass arguments to docker by add ARGS as an environment variable, for example:

```bash
ARGS="-p 8000:8000" npm start
ARGS="-p 8000:8000" node index.js
```

## Globals will not work
You can install globals, and they will be saved in your host's `~/.node_modules` directory. But they will not be linked when you run a new node instance. There is a solution that will come soon, via [this issue](https://github.com/markwylde/node-but-in-docker/issues/1).

# Why would I want to do this?
Node and the npm ecosystem come with a lot of dependancies and code that may not be trusted. Instead of installing a bunch of code on your local computer, you can isolate it inside a docker container.
