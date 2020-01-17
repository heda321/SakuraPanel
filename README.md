# SakuraPanel
樱花内网穿透网页端源代码，2020 重制

由于时间匆忙，没有写自动安装程序，所有操作需要手动完成。

## 功能和特性
- 支持多用户
- 支持用户组配置
- 支持每个用户单独限速
- 支持每个用户单独限制流量
- 可配置签到获得流量
- API 和主站可分离
- 实时流量统计
- 美观的界面

## 安装和配置
首先将项目 clone 到本地
```
git clone https://github.com/ZeroDream-CN/SakuraPanel/
```
然后移动到网站目录，并设置权限
```
mv SakuraPanel/* /data/wwwroot/my.panel.com/
chown -R www:www /data/wwwroot/my.panel.com/
```
然后进入到网站目录，分别编辑以下三个文件，修改数据库信息

| 文件名 | 作用 |
| ------ | ------ |
| __/configuration.php__ | 网站核心配置文件，里面每个配置项都有介绍 |
| __/api/index.php__ | 用于对接 Frps，里面只需配置数据库 |
| __/daemon.php__ | 服务器守护进程，需要在命令行下运行，里面只需要配置数据库 |

配置完成后，使用 Navicat、phpMyAdmin 等数据库管理软件创建一个新的数据库，然后导入 `import.sql`。

导入完成后，打开网站，注册一个新账号，然后在数据库中设置这个账号的 __group__ 字段为 `admin` 即可设置为管理员。