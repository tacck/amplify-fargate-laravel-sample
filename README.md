# amplify-fargate-laravel-sample

## How to use

You should use `amplify` CLI and `composer`.

* https://docs.amplify.aws/
* https://getcomposer.org/

```
$ git clone https://github.com/tacck/amplify-fargate-laravel-sample.git

$ cd amplify-fargate-laravel-sample

$ amplify init
```

> Answer questions and enable container-based deployments. See this.
> https://aws.amazon.com/jp/blogs/mobile/zero-effort-container-deployment-for-graphql-and-rest-apis-and-web-hosting-with-amplify-cli/

```
$ amplify add api
```

> Answer `container` for "Provide a friendly name for your resource".
> 
> Answer `Custom` for "What image would you like to use".

```
$ cp -r container/src amplify/backend/api/container

$ pushd amplify/backend/api/container/src/php/web
$ composer create-project --prefer-dist laravel/laravel laravel
$ popd

$ amplify push
```

> Answer `web` for "Select which container is the entrypoint"

```
✔ All resources are updated in the cloud

REST API endpoint: https://XXXXXXXXXX.execute-api.ap-northeast-1.amazonaws.com

$
```

Access above URL and you can see Laravel first page!

## Stop Fargate

I can't find menu for "Stop Fargate".
So, we should `remove api` or `delete`.

### remove api

```
$ amplify remove api
$ amplify push
```

> **Warning!**
> 
> This operation removes `amplify/backend/api/container` directory.

### delete

```
$ amplify delete
```

> **Warning!**
> 
> This operation deletes this project.
