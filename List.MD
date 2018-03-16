### Javascript
Event Loop -https://www.youtube.com/watch?v=8aGhZQkoFbQ

Functional Programming - https://www.youtube.com/watch?v=e-5obm1G_FY

Closure- https://jsfiddle.net/SyamSankar/9rorkvoo/

Currying in JavaScript
=====================
example :
const addResource = resourcePermission => componentCode => {
  return (
    !componentCode ||
    !resourcePermission[componentCode] ||
    resourcePermission[componentCode] !== 'HIDE'
  );
};

export default function resourceFilter(resources) {
  return (dispatch, getState) => {
    const resourcePermission = getState().resourcePermission;
    return resources.reduce((_resources, resource) => {
      if (addResource(resourcePermission)(resource[componentCode]))
        _resources.push(resource);
      return _resources;
    }, []);
  };
}



### NodeJS

To check knowledge -https://edgecoders.com/how-well-do-you-know-node-js-36b1473c01c8

Scaling - http://adrianmejia.com/blog/2016/03/23/how-to-scale-a-nodejs-app-based-on-number-of-users/

mongoose-express-crud - https://www.npmjs.com/package/mongoose-express-crud

Yeoman generator for a starter API -https://www.npmjs.com/package/generator-studio-api

craftninja/exp-starter-api -https://github.com/craftninja/exp-starter-api

Routing automated (Ben) - https://github.com/CognizantStudio/digital-supply-chain-services/

```
Mock Socket - https://github.com/thoov/mock-socket

https://www.npmjs.com/package/socket.io-mock

```


### Node Docker

http://bitjudo.com/blog/2014/03/13/building-efficient-dockerfiles-node-dot-js/


### React

React Strap-https://reactstrap.github.io/components/alerts/

Create-react-app with redux -https://github.com/reedsa/create-react-app-templates#redux

Error Handling - https://reactjs.org/blog/2017/07/26/error-handling-in-react-16.html

Redux Form - https://redux-form.com/7.3.0/

### Circle CI
I spent some time today digging into the CircleCI race condition that some of us have seen with our v2.0 builds using a database. I suspect that this issue could happen with any multi-image build.

The issue has been discussed here https://discuss.circleci.com/t/prevent-race-conditions-by-waiting-for-services-with-dockerize/11215 and here https://discuss.circleci.com/t/problem-waiting-for-postgres-with-dockerize/15059

I tested out a few different options with the team 6 server both on my local laptop using the CircleCI CLI (see https://circleci.com/docs/2.0/local-jobs/ for how to do that) and on the CircleCI server. I tried setting various environment variables at different points, I tried to install dockerize to make sure it was actually present before calling it, I tried the brute force method of seeing if postgres was running via a psql call.

I then stumbled upon https://circleci.com/docs/2.0/executor-types/#using-multiple-docker-images which states the following: *In a multi-image configuration job, all steps are executed in the container created by the first image listed.*

I also found this reference (https://discuss.circleci.com/t/using-psql-command-in-circleci-2-0-build/14785) that mentions psql, and I added a step to install the postgres client in my config file like this:

```      - run: dockerize -wait tcp://localhost:5432 -timeout 1m
      - run:
          name: Installing Dependencies
          command: |
            yarn install
            sudo apt-get install postgresql-client
```


After this config change, the server builds have been successfully running on CircleCI (at least so far). I'd be curious to hear if this helps any other builds. If I have more time tomorrow I'll try to dig in more. Here is the config for the team 6 server: https://github.com/CognizantStudio/lp02-team-6-mock-server/blob/master/.circleci/config.yml

### NodeJS - Profiling


https://nodejs.org/en/docs/guides/simple-profiling/

### Visual Studio Code

https://www.smashingmagazine.com/2018/01/visual-studio-code/


### Docker

https://github.com/CognizantStudio/docker-images

https://training.docker.com/introduction-to-docker

https://training.docker.com/docker-fundamentals

https://training.docker.com/docker-operations

https://github.com/CognizantStudio/docker-images

### Linting


https://github.com/standard/standard


### Python
https://www.blog.pythonlibrary.org/2018/03/13/python-3-an-intro-to-f-strings/
