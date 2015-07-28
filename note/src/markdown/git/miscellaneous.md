#Miscellaneous

- How to use git with proxy

Http Proxy:

```
git config --global http.proxy 'http://127.0.0.1:1080'
git config --global https.proxy 'https://127.0.0.1:1080'
```

Socks Proxy:

```
git config --global http.proxy 'socks5://127.0.0.1:7070'
git config --global https.proxy 'socks5://127.0.0.1:7070'
```
See more on [Stack Overflow](http://stackoverflow.com/questions/783811/getting-git-to-work-with-a-proxy-server)