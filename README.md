# Web Notepad

在线文本文档

## 安装

打开文件 `index.php`, 将 `$base_url` 改为自己的网站域名+目录名
（如：http://hehudieyiqi.com/notes,注意区分http和https）;

确保文件夹 `_tmp` 可以写入.


### Nginx 服务器

修改配置文件如下:

如果此程序在根目录下:
```
location / {
    rewrite ^/([a-zA-Z0-9_-]+)$ /index.php?note=$1;
}
```

如果此程序不在根目录下:
```
location ~* ^/notes/([a-zA-Z0-9_-]+)$ {
    try_files $uri /notes/index.php?note=$1;
}
```
