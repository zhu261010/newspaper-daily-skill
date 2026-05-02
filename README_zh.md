# newspaper-daily-skill

<div align="right">
  <a href="README.md">English</a> | <a href="README_zh.md">简体中文</a>
</div>

一个用于生成“报纸风格页面 + 深度浏览”的 Claude skill。

它可以把项目进展、日报内容、专题资料组织成全屏报纸布局，并支持词条链式跳转。

## 演示

![newspaper-daily-skill demo](assets/demo/demo.png)

## 核心能力

- 报纸风格 HTML 模板
- 深度浏览路由 `#/entry/<id>`
- 链式内部跳转与面包屑导航
- 日报/项目报/专题报通用 JSON 结构
- 移动端单栏阅读兼容
- 打印导出 PDF 友好

## 仓库结构

- `SKILL.md` - skill 元数据与使用指引
- `assets/template/index.html` - 全屏报纸模板
- `assets/template/examples/mvp.json` - 含深度词条关系的示例数据

## 命名规则

- 日报：`YYYY-MM-DD.json` 和 `YYYY-MM-DD.html`
- 项目报：`projects/<repo-or-folder-name>/index.json`
- 专题报：`topic-<slug>-YYYY-MM-DD.json`
- 词条 ID：`<domain>-<slug>`

## 数据字段（核心）

- `feed[].entryId`：头版条目跳转到词条
- `entries[]`：深度浏览词条库，包含：
  - `id`
  - `title`
  - `content`
  - `links[]`（`targetId`, `label`）

## 典型使用场景

1. 个人日报与团队晨报
2. 项目里程碑与风险同步
3. 专题研究与事故复盘
4. 可钻取的知识库展示

## 在其他项目复用

1. 复制 `assets/template/index.html` 到目标项目根目录。
2. 复制 `assets/template/examples/mvp.json` 到目标项目的 `examples/`。
3. 按你的内容替换 JSON，保持字段结构不变。
4. 直接打开 `index.html` 或启动静态服务预览。

静态服务示例：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

## 许可证

按你的项目策略使用。若需要，可在仓库中补充 License 文件。
