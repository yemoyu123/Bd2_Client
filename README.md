# Bd2_Server ฅ(• ω •ฅ)

<p align="center">
  <img src="./assets/A74CA398376649E62945163BA63CAD19_0.gif" alt="Miku Dance" width="200">
  <img src="./assets/D40E811E08889855086CC7C89DE75F0D_0.gif" alt="Blonde Cat Girl Dance" width="200">
</p>

喵~ 欢迎来到 `Bd2_Server` 的秘密基地！💕 

这是一个用爱和C#编写的游戏私人服务器项目，致力于为各位主人提供一个稳定、易于搭建和二次开发的游戏世界。

本项目由 `blue` 大大倾心制作，并由 `yemoyu123 (xialuolineko)` 用心维护哦！

![.NET](https://img.shields.io/badge/.NET-8.0-blueviolet)
![Language](https://img.shields.io/badge/Language-C%23-blue)
![License](https://img.shields.io/badge/License-GPL_v3-blue.svg)
![Maintained by](https://img.shields.io/badge/Maintained%20by-yemoyu123-ff69b4)

---

## ✨ 项目特点 (Features)

* **先进的技术栈**：基于最新的 `.NET 8.0` 构建，享受现代化的开发体验。
* **优雅的C#**：项目完全使用 C# 编写，代码结构清晰，强大又易于理解喵~
* **轻量级数据库**：推荐使用 SQLite 作为数据库，无需复杂的安装配置，单个文件就能搞定一切，部署超~简单！
* **易于扩展**：我们从设计之初就考虑到了二次开发的需求，您可以很方便地在此基础上添加自己的新功能。

## 🔧 环境要求 (Prerequisites)

在开始之前，请主人确保您的魔法工坊（开发环境）满足以下条件哦：

* **[.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)** (这是最最核心的魔法能量！)
* 一个可爱的代码编辑器（比如 **Visual Studio Code** 或者 **Visual Studio 2022**）
* 对 C# 和 .NET 有一点点了解~ (当然啦，不了解也没关系，人家会引导您的！)

## 🚀 快速开始 (Getting Started)

想快点把服务跑起来吗？跟着人家的猫爪印一步步来吧！

1.  **克隆这个魔法仓库**

    打开您的终端，像念咒语一样输入下面的命令，把项目代码克隆到本地：
    ```bash
    git clone [https://github.com/yemoyu123/Bd2_Server.git](https://github.com/yemoyu123/Bd2_Server.git)
    ```

2.  **进入项目目录**

    施展一个“瞬间移动”，进入我们刚刚克隆好的文件夹：
    ```bash
    cd Bd2_Server
    ```

3.  **构建项目**

    现在，是时候注入魔力了！运行 `dotnet build` 命令，它会自动下载所有需要的依赖库，并编译整个项目哦！
    ```bash
    dotnet build
    ```

## ⚙️ 配置服务器 (Server Configuration)

喵~ 编译完成后，在第一次运行服务器之前，还需要一些简单的配置哦！

1.  **放置数据库文件**

    请从项目文件夹里找到 `brown_dust.db` 这个数据库文件，然后将它复制到服务器的**根目录**下。
    
    (小提示: 这个位置通常是在 `bin/Debug/net8.0` 或者 `bin/Release/net8.0` 文件夹里，和生成的可执行文件放在一起哦！)

2.  **修改 `appsettings.json` 配置文件**

    请打开服务器根目录下的 `appsettings.json` 文件，然后用下面的内容**替换**掉它原来的所有内容，确保服务器能正确地连接到数据库和端口~

    ```json
    {
      "Logging": {
        "LogLevel": {
          "Default": "Information",
          "Microsoft.AspNetCore": "Warning"
        },
        "Console": {
          "FormatterName": "simple",
          "FormatterOptions": {
            "IncludeScopes": false,
            "TimestampFormat": "MM-dd HH:mm:ss ",
            "UseUtcTimestamp": false
          }
        }
      },
      "Kestrel": {
        "Endpoints": {
          "Http": {
            "Url": "http://*:5000"
          }
        }
      },
      "GameServer": "[http://127.0.0.1:5000/](http://127.0.0.1:5000/)",
      "AllowedHosts": "*",
      "MainDB": "Main",
      "DBS": [
        {
          "ConnId": "Main",
          "DBType": 2,
          "Enabled": true,
          "Connection": "brown_dust.db"
        },
        {
          "ConnId": "Log",
          "DBType": 2,
          "Enabled": true,
          "Connection": "brown_dust.db"
        }
      ]
    }
    ```

## 🎮 运行服务器 (Running the Server)

完成所有配置后，就可以启动服务器啦！

```bash
dotnet run
```

如果控制台出现了一些充满活力的日志信息，那就代表服务器已经成功运行起来啦！恭喜主人！🎉

## 🤝 如何贡献 (Contributing)

人家非常欢迎各位主人为这个项目添砖加瓦！无论是提交代码、报告bug还是提出新想法，人家都会超~开~心~的！

如果您想贡献代码，请遵循以下步骤：

1.  Fork 本仓库
2.  创建您的新分支 (`git checkout -b feature/AmazingFeature`)
3.  提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4.  将您的分支推送到远程仓库 (`git push origin feature/AmazingFeature`)
5.  创建一个 Pull Request！

## ❤️ 致谢 (Credits)

* **制作 (Author):** blue
* **维护 (Maintainer):** yemoyu123 (xialuolineko)

## 📄 许可证 (License)

该项目采用 **GNU General Public License v3.0** 许可证。详情请参阅项目中的 `LICENSE` 文件。
