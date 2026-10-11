# 薄肌黄毛 · Boji Huangmao

把 AI 辅助记录、身体习惯、抗评价干扰和机会探索，转成可执行、可检查、可调整的个人行动指南。

这是一个中文 Codex Skill，适合需要把个人成长目标拆成具体行动的人。当前版本 **v1.0.0** 为初始文本技能，已校验结构与打包完整性，尚无长期效果验证。

**[下载技能包](artifacts/薄肌黄毛.skill)** · **[阅读行动指南](artifacts/行动指南.md)** · **[主要观点与来源](artifacts/主要观点与来源.md)** · **[Releases](https://github.com/orange90/boji-huangmao/releases)**

## 包含什么

- 现状诊断与六个执行模块：AI 记录、身体习惯、面对评价、机会探索、保留选择空间、创造与更新。
- 一周启动与可调整的 30 天实践安排。
- 现状卡、实验卡、每日日志、评价处理卡与每周复盘。
- 原视频时间定位、来源可信度说明与编辑取舍。

## 安装 / Installation

需要支持本地 Skill 的 Codex 环境。技能本身是 Markdown/YAML，没有运行时代码、额外 API 或付费订阅要求；使用的 AI 服务是否收费取决于你的环境。当前只核验了本地文件结构，未做跨客户端兼容性测试。

下载此仓库后，将 `skills/boji-huangmao` 文件夹复制到你的 Codex 技能目录，通常为 `~/.codex/skills/`；如果设置了 `CODEX_HOME`，则使用其下的 `skills/`。已有同名技能时先备份再替换。

使用终端安装（需要 Git 与 shell；目标目录已存在时会停止，避免覆盖）：

```bash
git clone https://github.com/orange90/boji-huangmao.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
if [ ! -e "${CODEX_HOME:-$HOME/.codex}/skills/boji-huangmao" ]; then
  cp -R boji-huangmao/skills/boji-huangmao "${CODEX_HOME:-$HOME/.codex}/skills/boji-huangmao"
else
  echo "同名技能已存在，请先备份，再决定是否替换。"
fi
```

也可以下载 `.skill` 包。它是 ZIP 格式压缩包；解压后得到 `boji-huangmao/` 文件夹，按上述方式安装。不假设所有客户端都支持双击导入 `.skill`。

如当前会话未发现新技能，重新开启会话。调用示例：

```text
请用 $boji-huangmao 制定本周行动指南。
我每周有 5 小时，想验证自己能否做出一个实用的 AI 整理工具。
请只选一个主要瓶颈，列出今天一步、本周交付、完成证据、预算上限和停止条件。
```

预期得到一份针对现状的行动计划，而非自动执行任务。技能不会自行报名、付款、对外联系或发布内容。

升级：备份后替换技能文件夹。卸载：删除该文件夹；你另行创建的行动记录不受影响。

## 文件导航

| 路径 | 用途 |
|---|---|
| `skills/boji-huangmao/SKILL.md` | 技能入口 |
| `skills/boji-huangmao/agents/openai.yaml` | 中文展示名与调用示例 |
| `skills/boji-huangmao/references/` | 行动方法与来源 |
| `artifacts/薄肌黄毛.skill` | 可分发技能包 |
| `artifacts/行动指南.md` | 独立阅读版 |
| `artifacts/主要观点与来源.md` | 独立来源说明 |
| `artifacts/SHA256SUMS.txt` | 下载文件 SHA-256 |

## 来源与边界

灵感来自 [邵艾伦与孙宇晨的访谈](https://www.youtube.com/watch?v=0Z-vhBvBmUY)。整理依据为 [公开转录](https://github.com/D-sudoasd/justin-sun-ai-transcript)，未逐句听校原视频，也未独立证实其中的经历和商业数据。仓库不含完整逐字稿、视频或音频。

执行流程、表格与周期是 AI 辅助整理后的改编，不是嘉宾原话，不代表嘉宾背书。它不等同于独立的《薄肌圣经》或“黄毛思维”教程，也不提供诊疗、投资保证或关系操控方法。

技能本身不联网、不采集数据；实际调用它的 AI 客户端可能将输入发送给其服务商，请按你使用的平台设置处理个人资料。不要在 Issues 上传健康隐私、密钥或个人日志。

## 反馈与许可

欢迎通过 [Issues](https://github.com/orange90/boji-huangmao/issues) 提交具体改进建议，附上去除个人信息的输入、实际输出与预期行为。改进时请保留来源边界，区分观点、事实与新增方法。

本仓库原创技能说明与行动模板采用 [MIT License](LICENSE)。所链接的第三方视频、转录及其他资料不在此授权范围内，其权利归原权利人所有。
