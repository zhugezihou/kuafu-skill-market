# 🧠 夸父技能市场 (Kuafu Skill Market)

夸父（Kuafu）AI Agent 的远程技能仓库 — 技能发现、分发与共享平台。

## 什么是技能包？

技能包（kfskill）是夸父的可执行知识单元。每个技能包是一个 `.yaml` 文件，包含：

- **元数据**：名称、描述、版本、作者、分类、关键词
- **执行步骤**：有序的任务描述，LLM 按步骤执行
- **注意事项**：常见陷阱和最佳实践
- **依赖声明**：所需的系统工具和 Python 包

## 如何安装技能

```bash
# 从本仓库安装技能
kuafu skill install <技能名称>

# 从 URL 安装
kuafu skill install https://raw.githubusercontent.com/zhugezihou/kuafu-skill-market/main/skills/技能名称.yaml

# 配置远程仓库（夸父会自动从本仓库搜索技能）
export KUAFFU_SKILL_REPOS='[{"name":"kuafu-market","url":"https://raw.githubusercontent.com/zhugezihou/kuafu-skill-market/main/index.json"}]'
```

## 技能分类

| 分类 | 说明 |
|------|------|
| `coding` | 编程开发相关 |
| `web` | 网页抓取、浏览器自动化 |
| `research` | 信息检索、论文阅读 |
| `devops` | 部署、运维、CI/CD |
| `media` | 图像、音视频处理 |
| `writing` | 写作、翻译、润色 |
| `data-science` | 数据分析、可视化 |
| `productivity` | 效率工具 |
| `communication` | 飞书、微信通知 |
| `general` | 通用/未分类 |

## 如何贡献

1. 在 `skills/` 目录下创建 `.yaml` 文件（遵循 kfskill 格式）
2. 更新 `index.json` 添加新技能条目
3. 提交 PR

### kfskill 格式规范

```yaml
name: 技能名称              # 必填
description: 一行描述        # 必填
version: 1.0.0              # 推荐
author: 作者名               # 可选
category: coding            # 可选
keywords:                   # 推荐
  - 关键词1
  - 关键词2
steps:                      # 必填
  - 第一步做什么
  - 第二步做什么
pitfalls:                   # 可选
  - 注意事项
```

## 许可证

MIT
