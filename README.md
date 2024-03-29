# prerendercloud-iis

<img align="right" src="https://cloud.githubusercontent.com/assets/22159102/21554484/9d542f5a-cdc4-11e6-8c4c-7730a9e9e2d1.png">

IIS web.config for pre-rendering JavaScript single page apps with [Headless-Render-API.com](https://headless-render-api.com) (formerly named prerender.cloud from 2016 - 2022)

## Usage

It's possible your IIS server may already have steps 1 and 2 and 4 mostly done already - in which case, just go to step 5.

1. use the `Web Platform Installer` to install "URL Rewrite" (see more [here](https://stackoverflow.com/questions/25997830/how-can-i-enable-url-rewrite-module-in-iis-8-5-in-server-2012) if having problems)
2. use the `Web Platform Installer` to install "Application Request Routing"
    * [Enable reverse proxy in "Application Request Routing" for your site](https://weblogs.asp.net/owscott/creating-a-reverse-proxy-with-url-rewrite-for-iis)
3. restart IIS entirely
4. create a file (if it doesn't already exist) named `web.config` and put it in the root of the directory serving your website
5. add a server variable for `HTTP_X_PRERENDER_TOKEN` (see screenshot below)
6. modify [web.config](./web.config)
    * add your Headless-Render-API.com API token
    * hardcode the protocol in the `url` attr of the `<action type="Rewrite" />` tag to be (http or https) for your site

![image](https://user-images.githubusercontent.com/22159102/51094611-89651f00-177c-11e9-820c-a9fc22c045fa.png)


![image](https://user-images.githubusercontent.com/22159102/51094580-4e62eb80-177c-11e9-9be5-c7dbf906ade3.png)


