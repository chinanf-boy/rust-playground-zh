
## 配置

在开发时,您可以将它们放一个[`.env`][dotenv]文件在此目录中的磁盘上.

在生产中,应根据您选择的部署方法进行设置.

| 键                         | 必须    | 默认值       | 描述                        |
| ------------------------- | ----- | --------- | ------------------------- |
| `PLAYGROUND_UI_ROOT`      | **是** |           | HTML,CSS和Javascript文件的路径  |
| `PLAYGROUND_GITHUB_TOKEN` | **是** |           | 该[GitHub API令牌][gist]读写gist |
| `PLAYGROUND_UI_ADDRESS`   | 没有    | 127.0.0.1 | 要听的地址                     |
| `PLAYGROUND_UI_PORT`      | 没有    | 5000      | 要听的端口                     |
| `PLAYGROUND_LOG_FILE`     | 没有    | access-log.csv | 用于记录访问的文件                 |
| `TMPDIR`                  | 没有    | 系统提供的     | 将保存编译工件的位置.必须可以访问Docker   |

[dotenv]: https://crates.io/crates/dotenv

[gist]: https://developer.github.com/v3/gists/#authentication
