# liuxie-skills

适用于 [OpenCode](https://opencode.ai) 的 AI Skills 集合。

---

## 已有 Skills

### prd-review

**PRD 评审委员会** - 一个全方位的产品需求文档 (PRD) 质量审计工具。

#### 功能特点

- **三方评审视角**：产品总监 + 首席架构师 + 测试负责人
- **双维度评分**：逻辑分 (70%) + 结构分 (30%)
- **决策树驱动**：每项评判都有明确的判定路径
- **证据主义**：所有扣分必须引用原文作为证据

#### 评分模型

```
最终得分 = (逻辑分 × 70%) + (结构分 × 30%)
```

| 等级 | 分数 | 结论 |
|:---:|:---:|:---|
| S | ≥ 85 | ✅ 批准 - 直接进入开发 |
| A | 70-84 | ⚠️ 微修 - PM 修正后确认 |
| B | 60-69 | 🚧 重修 - 二次评审 |
| C | < 60 | ⛔️ 驳回 - 打回重构 |
| D | 0 | 🚫 拒收 - 结构残缺 |

#### 文件结构

```
prd-review/
├── SKILL.md                    # 主技能定义
├── scripts/
│   └── analyze_prd_meta.py     # 元数据分析脚本
└── references/
    ├── buzzwords.md            # 虚词黑名单 (200+)
    └── compliance.md           # 合规红线规则
```

#### 使用方法

在 OpenCode 中使用：

```
/prd-review <PRD文件路径>
```

---

## 安装

将 skill 目录复制到 OpenCode 的 skills 目录：

```bash
# macOS / Linux
cp -r prd-review ~/.config/opencode/skills/

# 或克隆整个仓库
git clone https://github.com/liuxie85/liuxie-skills.git ~/.config/opencode/skills/liuxie-skills
```

---

## 许可证

MIT License
