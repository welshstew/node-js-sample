# node-js-sample

A barebones Node.js app using [Express 4](http://expressjs.com/).

Forked from [GitHub](https://github.com/heroku/node-js-sample).

## Running Locally

Make sure you have [Node.js](http://nodejs.org/) and the [Heroku Toolbelt](https://toolbelt.heroku.com/) installed.

```sh
git clone git@github.com:heroku/node-js-sample.git # or clone your own fork
cd node-js-sample
npm install
npm start
```

Your app should now be running on [localhost:5000](http://localhost:5000/).

## Deploying to Heroku

```
heroku create
git push heroku master
heroku open
```

## Deploying to OpenShift

```
oc new-project nodejs

#add the template..
oc create -f kube/nodejs-template.yaml

#get the docker registry ip
export REGISTRY_IP=$(oc get svc/docker-registry -n default -o json | jq .spec.clusterIP)
oc new-app --template=nodejs-sample -pREGISTRY_IP=${REGISTRY_IP} 

```


## Documentation

For more information about using Node.js on Heroku, see these Dev Center articles:

- [10 Habits of a Happy Node Hacker](https://blog.heroku.com/archives/2014/3/11/node-habits)
- [Getting Started with Node.js on Heroku](https://devcenter.heroku.com/articles/getting-started-with-nodejs)
- [Heroku Node.js Support](https://devcenter.heroku.com/articles/nodejs-support)
- [Node.js on Heroku](https://devcenter.heroku.com/categories/nodejs)
- [Using WebSockets on Heroku with Node.js](https://devcenter.heroku.com/articles/node-websockets)
