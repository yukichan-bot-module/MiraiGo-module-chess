# MiraiGo-module-chess

ID: `com.aimerneige.chess`

Module for [MiraiGo-Template](https://github.com/Logiase/MiraiGo-Template)

## 说明

本项目是 [MiraiChess](https://github.com/aimerneige/MiraiChess) 的模块化版本，用于方便整合入其他机器人。如果你只是想部署一个国际象棋机器人，请查阅 [MiraiChess](https://github.com/aimerneige/MiraiChess)。

一般地，为保证稳定性，本模块会落后主仓库几个版本，如果你想要体验新功能，请使用 [MiraiChess](https://github.com/aimerneige/MiraiChess)。

## 功能

- 可以在群内下国际象棋
- 支持 elo 等级分计算
- 发送「帮助」或「help」获取帮助

## 使用方法

#### 安装依赖项

- 你必须拥有 Linux 环境 [Windows 支持性说明](https://github.com/aimerneige/MiraiChess#%E6%98%AF%E5%90%A6%E6%94%AF%E6%8C%81-windows)
- [python](https://www.python.org/downloads/)
- [python-chess](https://github.com/niklasf/python-chess)\
`pip install python-chess`
- [pgn2gif](https://github.com/dn1z/pgn2gif)\
`git clone https://github.com/dn1z/pgn2gif.git && cd pgn2gif && sudo python setup.py install`
- [inkscape](https://inkscape.org/)\
直接执行 `download_inkscape.sh` 即可

#### 在适当位置引用本包

```go
package example

imports (
    // ...

    _ "github.com/yukichan-bot-module/MiraiGo-module-chess"

    // ...
)

// ...
```

在全局配置文件中填入配置文件路径，不填默认为 `./chess.yaml`。

```yaml
aimerneige:
  chess:
    path: "./config/chess.yaml"
```

修改你的配置文件

```yaml
disallowed: # 不提供服务的群聊列表
  - 741535071
  - 731500560
blacklist: # 黑名单用户列表
  - 1781924496
elo:
  enable: false # 是否启用 elo 等级分计算功能
  default: 500 # 玩家默认等级分
  db: # 数据库
    type: sqlite # mysql | sqlite
    mysql:
      username: root
      password: password
      host: localhost
      port: 3306
      database: example
      charset: utf8mb4
    sqlite:
      path: "./db/chess.db"
inkscape: "./bin/inkscape" # inkscape 可执行文件路径
temp: "./temp/" # 临时文件夹，用于存放脚本生成的棋盘图片
```

## LICENSE

<a href="https://www.gnu.org/licenses/agpl-3.0.en.html">
<img src="https://www.gnu.org/graphics/agplv3-155x51.png">
</a>

本项目使用 `AGPLv3` 协议开源，您可以在 [GitHub](https://github.com/yukichan-bot-module/MiraiGo-module-fortune) 获取本项目源代码。为了整个社区的良性发展，我们强烈建议您做到以下几点：

- **间接接触（包括但不限于使用 `Http API` 或 跨进程技术）到本项目的软件使用 `AGPLv3` 开源**
- **不鼓励，不支持一切商业使用**
