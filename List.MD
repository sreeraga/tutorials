### Javascript
Event Loop -https://www.youtube.com/watch?v=8aGhZQkoFbQ

Functional Programming - https://www.youtube.com/watch?v=e-5obm1G_FY

http://thecodebarbarian.com/basic-functional-programming-with-async-await.html

Closure- https://jsfiddle.net/SyamSankar/9rorkvoo/

Currying in JavaScript
```
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
```
- [Single Responsibility Principle: A Recipe for Great Code](https://www.toptal.com/software/single-responsibility-principle)

- [5 Principles that will make you a SOLID JavaScript Developer](https://thefullstack.xyz/solid-javascript/)

- [S.O.L.I.D The first 5 principles of Object Oriented Design with JavaScript](https://medium.com/@cramirez92/s-o-l-i-d-the-first-5-priciples-of-object-oriented-design-with-javascript-790f6ac9b9fa)

### NodeJS

To check knowledge -https://edgecoders.com/how-well-do-you-know-node-js-36b1473c01c8

Scaling - http://adrianmejia.com/blog/2016/03/23/how-to-scale-a-nodejs-app-based-on-number-of-users/

mongoose-express-crud - https://www.npmjs.com/package/mongoose-express-crud

Yeoman generator for a starter API -https://www.npmjs.com/package/generator-studio-api

craftninja/exp-starter-api -https://github.com/craftninja/exp-starter-api

Routing automated (Ben) - https://github.com/CognizantStudio/digital-supply-chain-services/

Avoid unhandled promise rejection DeprecationWarnings in Node - https://medium.com/@kyle.mickey/a-practical-guide-to-avoid-unhandled-promise-rejection-deprecationwarnings-in-node-f9c67634dd2b

Basic Functional Programming With Async/Await : http://thecodebarbarian.com/basic-functional-programming-with-async-await.html

**npm ci** -https://docs.npmjs.com/cli/ci

Error handling with async/await and promises - https://dev.to/vcarl/error-handling-with-asyncawait-and-promises-2eoa

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

Reach Router - https://reach.tech/router

Fragment Driven UIs with Apollo - https://medium.com/@abhiaiyer/fragment-driven-uis-with-apollo-17d933fa1cbe

### NodeJS - Profiling

https://nodejs.org/en/docs/guides/simple-profiling/

### Visual Studio Code

https://www.smashingmagazine.com/2018/01/visual-studio-code/

Introducing GraphQL for Visual Studio Code : https://www.prisma.io/blog/vscode-thieghu7shoo/


### Docker

https://github.com/CognizantStudio/docker-images

https://training.docker.com/introduction-to-docker

https://training.docker.com/docker-fundamentals

https://training.docker.com/docker-operations

https://github.com/CognizantStudio/docker-images

```
To go inside container : docker exec -it CONTAINER_NAME sh
To check connectivity with other container: ping -c 4 CONTAINER_NAME
        curl http://CONTAINERNAME:PORT?<query string from log outputs>
```

### Linting


https://github.com/standard/standard

 #### EsLint
      1.    npm install eslint --save-dev
      2.    ./node_modules/.bin/eslint –init
        a.    Choose `> Use a popular style guide`
        b.    Select `> Airbnb`
        c.    Select config file format as `YAML` (I prefer yamal )
      3.    After installation add the following configuration inside the generated `.eslintrc.yml` file
            ```extends: airbnb-base
            env:
              es6: true
              node: true
              mocha: true
            rules:
              linebreak-style:
                - error
                - windows
              no-use-before-define:
                - off
              arrow-parens:
                - error
                - as-needed```
      4.    Add file `.eslintignore` in root directory with folders and files to be ignored
      Eg.. migrations/*
      models/*
      5.    Add script in package.json for lint
      "lint": "./node_modules/.bin/eslint . "


### Python
https://www.blog.pythonlibrary.org/2018/03/13/python-3-an-intro-to-f-strings/

https://py.checkio.org/blog/5-best-speeches-mr-raymond-hettinger/

How to write Dockerfiles for Python Web Apps https://blog.hasura.io/how-to-write-dockerfiles-for-python-web-apps-6d173842ae1d

python-keycloak-client : https://pypi.org/project/python-keycloak-client/

Python Cuncurrency : https://www.youtube.com/watch?v=MCs5OvhV9S4

### Ruby & Rails

ActiveRecord migration: http://edgeguides.rubyonrails.org/active_record_migrations.html

https://www.sandimetz.com/blog/https://www.sandimetz.com/blog/

https://robots.thoughtbot.com/how-we-test-rails-applications

Nice resource on rspec (http://www.betterspecs.org/) and for more information on shared examples (https://medium.freecodecamp.org/how-to-dry-out-your-rspec-tests-using-shared-examples-d5cc5d33fd76)

### Git
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow

https://www.youtube.com/watch?v=0SJCYPsef54

https://www.atlassian.com/git/tutorials/advanced-overview

https://robots.thoughtbot.com/git-interactive-rebase-squash-amend-rewriting-history

.gitattributes - This file can be used ......

### JWT
https://stormpath.com/blog/where-to-store-your-jwts-cookies-vs-html5-web-storage

### GraphQL
https://graphql.guide/

### Flex and Grid

http://grid.malven.co/
http://flexbox.malven.co/

### Refactoring
https://refactoring.guru/refactoring

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

