以下是你提供的 Markdown 内容的中文翻译，保持了原始格式和结构：

---

<div align="center">
  <sup>特别感谢：</sup>
  <br>
  <a href="https://www.warp.dev/drawdb/" target="_blank">
    <img alt="Warp 赞助" width="280" src="https://github.com/user-attachments/assets/c7f141e7-9751-407d-bb0e-d6f2c487b34f">
    <br>
    <b>面向所有平台的新一代 AI 驱动智能终端</b>
  </a>
</div>

<br/>
<br/>

<div align="center">
    <img width="64" alt="drawdb logo" src="./src/assets/icon-dark.png">
    <h1>drawDB</h1>
</div>

<h3 align="center">免费、简单且直观的数据库模式编辑器和 SQL 生成器。</h3>

<div align="center" style="margin-bottom:12px;">
    <a href="https://drawdb.app/" style="display: flex; align-items: center;">
        <img src="https://img.shields.io/badge/开始构建-grey" alt="drawDB"/>
    </a>
    <a href="https://discord.gg/BrjZgNrmR6" style="display: flex; align-items: center;">
        <img src="https://img.shields.io/discord/1196658537208758412.svg?label=加入 Discord&logo=discord" alt="Discord"/>
    </a>
    <a href="https://x.com/drawDB_" style="display: flex; align-items: center;">
        <img src="https://img.shields.io/badge/在X上关注我们-blue?logo=X" alt="在X上关注我们"/>
    </a>
</div>

<h3 align="center"><img width="700" style="border-radius:5px;" alt="演示" src="drawdb.png"></h3>

DrawDB 是一个功能强大且用户友好的数据库实体关系（DBER）编辑器，直接运行在你的浏览器中。只需几次点击即可创建图表、导出 SQL 脚本、自定义编辑器，无需注册账户即可使用更多功能。完整功能列表请[点击此处](https://drawdb.app/)。

## 开始使用

### 本地开发

```bash
git clone https://github.com/drawdb-io/drawdb
cd drawdb
npm install
npm run dev
```

### 构建项目

```bash
git clone https://github.com/drawdb-io/drawdb
cd drawdb
npm install
npm run build
```

### Docker 构建

```bash
docker build -t drawdb .
docker run -p 3000:80 drawdb
```

如果你希望使用文件共享功能，请根据 `.env.sample` 文件设置[服务器](https://github.com/drawdb-io/drawdb-server)和环境变量。除非你需要共享文件，否则不需要进行此操作。