![image](https://cloud.githubusercontent.com/assets/22159102/21554484/9d542f5a-cdc4-11e6-8c4c-7730a9e9e2d1.png)

# prerendercloud-iis

IIS web.config for [https://www.prerender.cloud/](https://www.prerender.cloud/) for **prerendering** (server-side rendering) webpages.

## Usage

It's possible your IIS server may already have steps 1 and 2 and 4 mostly done already - in which case, just go to step 5.

1. use the `Web Platform Installer` to install "URL Rewrite" (see more [here](https://stackoverflow.com/questions/25997830/how-can-i-enable-url-rewrite-module-in-iis-8-5-in-server-2012) if having problems)
2. use the `Web Platform Installer` to install "Application Request Routing"
    * [Enable reverse proxy in "Application Request Routing" for your site](https://weblogs.asp.net/owscott/creating-a-reverse-proxy-with-url-rewrite-for-iis)
3. restart IIS entirely
4. create a file (if it doesn't already exist) named `web.config` and put it in the root of the directory serving your website
5. modify [web.config](./web.config)
    * add your prerender.cloud API token
    * hardcode the protocol in the `url` attr of the `<action type="Rewrite" />` tag to be (http or https) for your site

![image](https://user-images.githubusercontent.com/16573/31325005-3c316b24-ac6d-11e7-99e5-5f73e4bc15d4.png)


Inspired from https://gist.github.com/blowsie/04c183c62a432f6450c9
