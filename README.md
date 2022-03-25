### 一键经测试本镜像占用内存资源较低，运行稳定。点击下方紫色图标部署。
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https%3A%2F%2Fgithub.com%2Fasswedrdf%2F56yhggh)

### 路径

`WebSocket` 路径(配置文件中的 `path` )为 `/` 
### 端口

`端口` 为 `443` 。

### UUID

`UUID` 默认为 `6aa45bb0-34c1-4949-bfc8-4f4531a5f037` 你也可以在部署时自由修改（建议修改）。

## 流量中转

使用cloudflare的workers来`中转流量`，配置为： 

```
addEventListener(
      "fetch",event => {
         let url=new URL(event.request.url);
         url.hostname="你的heroku域名.herokuapp.com";
         let request=new Request(url,event.request);
         event. respondWith(
           fetch(request)
         )
      }
    ) 
```






