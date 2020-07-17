# hello-world

## Project creation

### Install vue-cli
```
npm install -g @vue/cli
```

### Create project
```
vue create hello-world
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).

## Run with Docker locally

### Build image
```
docker build -t hello-world .
```

### Run image
```
docker run -it -p 8080:8080 --rm --name docker-hello-world hello-world
```

## AWS Code Pipeline
The pipeline built with this app consists of a Github hook that triggers a build. The build server creates a docker container 
and pushes it to AWS Elastic Container Repository (ECR). Once this is done, Code Deploy creates an ECS cluster that runs the
docker container from ECR.

### Configuring Code Build
[Follow this link to configure Code Build](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-docker.html)

### Reminders for Code Pipeline
1. Create a repository in ECR
2. Make sure to configure environment variables in Code Build.
3. Make sure the service role for Code Build has the correct IAM policy. See the link above.
