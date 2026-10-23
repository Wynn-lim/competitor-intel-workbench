# 竞品情报工作台 + AI 编导 PRD（静态展示版）

两个作品共用一个 GitHub Pages 站点：

| 路径 | 内容 |
| --- | --- |
| `/` | 导航首页 |
| `/competitor-intel-workbench/` | 独角鲸·竞品情报工作台（只读静态版） |
| `/director/` | AI 编导 Agent PRD |

## 竞品情报工作台（静态版说明）

原系统由本地 Python 服务 + React 前端组成，支持自动采集、证据判定、人工层编辑。
GitHub Pages 只能托管静态文件，因此本仓库是**构建产物 + 数据快照**的只读版：

- 可看：总览、竞品库、竞品详情、事件、对比矩阵、政策、话术库、待核实清单、内容日历
- 只读快照：采集完成率、证据卡统计（来自 `collect_status.json`）
- 不可用（需要本地服务端）：启动采集、证据「采信/不采信」判定、对比摘要编辑与冻结、上传 .docx 回传、修改登录口令

> 数据口径：`data_as_of` 见工作台页面顶部。数据为构建时的快照，不会随本地库更新。

## 本地复现构建

```bash
cd workbench-src/app
node node_modules/vite/bin/vite.js build --base=/competitor-intel-workbench/ --outDir=dist-static
cp -r dist/data/. dist-static/data/   # 数据快照由 collector 导出脚本生成
```

## AI 编导 Agent PRD

`director/` 下是完整 PRD 页面（AI 编导工作台产品设计）。
