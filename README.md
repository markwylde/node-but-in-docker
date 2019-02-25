# What is this all about?
Instead of having to install node, npm and a bunch of dependancies on your local machine for every project you have, you can run node in a sandboxed Docker container.

# How do I install it?
There's not really an install process. You simply copy the files from the bin folder in this repo into your `/usr/local/bin` folder. Then you can run `node` or `npm` as normal, but it will spin up a new docker container.

```bash
git clone https://github.com/markwylde/node-but-in-docker.git
sudo cp ./bin/* /usr/local/bin
```

# Why would I want to do this?
Node and the npm ecosystem come with a lot of dependancies and code that may not be trusted. Instead of installing a bunch of code on your local computer, you can isolate it inside a docker container.
