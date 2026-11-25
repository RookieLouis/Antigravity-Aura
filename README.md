# Antigravity-Aura

[简体中文](#中文说明) · [English](#english)

## 中文说明

**Antigravity-Aura** 是一个面向 [Google Antigravity](https://antigravity.google/) 的全局/工作区插件包，整合了 Aura 桌面应用维护规范、Aura MCP 诊断、受保护蓝图读取、Unreal Engine 资产工作流以及 Aura 对话管理 4 项技能。

### 包含的技能

| 技能 | 路径 | 用途 |
| --- | --- | --- |
| `aura-app-workflow` | [skills/aura-app-workflow/SKILL.md](skills/aura-app-workflow/SKILL.md) | Aura 桌面应用维护、备份、本机对话缓存查找、图文报告与按月归档约定。 |
| `aura-conversations` | [skills/aura-conversations/SKILL.md](skills/aura-conversations/SKILL.md) | 查看、读取或同步真实 Aura 对话记录，附带项目关联脚本 [link-conversation-project.mjs](scripts/link-conversation-project.mjs)。 |
| `aura-diagnostics` | [skills/aura-diagnostics/SKILL.md](skills/aura-diagnostics/SKILL.md) | 诊断 Aura MCP 自检、连接失败、模型接入与权限策略拒绝，并在授权范围内修复配置。 |
| `unreal-workflow` | [skills/unreal-workflow/SKILL.md](skills/unreal-workflow/SKILL.md) | 定位、读取、修改并验证 Unreal Engine 工程的蓝图与其他资产（含只读保护与备份约定）。 |

### 安装到 Antigravity

#### 方式一：全局安装（对所有工作区生效）

将本仓库克隆或复制到 Antigravity 全局插件目录：

```powershell
git clone https://github.com/RookieLouis/Antigravity-Aura.git "$HOME\.gemini\config\plugins\antigravity-aura"
```

#### 方式二：工作区安装（仅对当前项目生效）

```powershell
git clone https://github.com/RookieLouis/Antigravity-Aura.git ".agents\plugins\antigravity-aura"
```

安装完成后，插件会自动被 Antigravity 发现并加载，可在 **Customizations / Plugins** 页面查看或开关；4 个技能从下一轮对话开始生效。

### 可选 MCP 配置说明

- `aura-app-workflow` 无需额外 MCP 服务即可独立使用。
- `aura-conversations`、`aura-diagnostics`、`unreal-workflow` 中的诊断与资产回读步骤会调用 Aura / Codex-Aura 提供的 MCP 工具（如 `aura_doctor`、`aura_permissions`、`aura_get_blueprint_meta`、`unreal_inspector`、`unreal_editor`）。如需在 Antigravity 中直接调用这些工具，请在本机插件目录中自行添加 `mcp_config.json` 或在全局 `~/.gemini/config/mcp_config.json` 中配置对应服务。

---

## English

**Antigravity-Aura** is an Antigravity plugin bundling four Aura and Unreal Engine workflow skills:

- **`aura-app-workflow`**: Maintenance, backup, local cache lookup, bilingual report packaging, and monthly archiving conventions for the Aura desktop app.
- **`aura-conversations`**: Listing, reading, and organizing Aura conversations with the accompanying [link-conversation-project.mjs](scripts/link-conversation-project.mjs) helper.
- **`aura-diagnostics`**: Layer-by-layer troubleshooting for Aura MCP handshakes, editor connectivity, model configuration, and permission guards.
- **`unreal-workflow`**: Safe Blueprint metadata/graph inspection, backup-before-edit checks, Aura best-practice loading, and readback verification for Unreal Engine projects.

### Installation

Clone into Antigravity's global plugins directory (applies to all workspaces):

```bash
git clone https://github.com/RookieLouis/Antigravity-Aura.git ~/.gemini/config/plugins/antigravity-aura
```

Or into a single workspace at `.agents/plugins/antigravity-aura`.

## License

MIT License — see [LICENSE](LICENSE).
