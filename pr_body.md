## 改动

将配图场景从米白色纸张质感改为透明背景 PNG，适配需要透明素材的场景。

### README.md
- 场景使用透明背景（替代米白色纸张质感）

### SKILL.md
- **Mode A**：deliver 指令改为生成透明 PNG（先用 `#00FF00` chroma-key 背景生成，再用 `scripts/cutout.py` 去背）
- **Mode A style anchor**：背景改为 `#00FF00 chroma-key background`
- **Mode B**：`<KEY_COLOR>` 硬编码为 `#00FF00`（与 Mode A 统一）

### 实现方式

AI 生图模型无法原生输出透明 PNG，因此 Mode A 与 Mode B 统一采用 chroma-key + cutout.py 的流程：先在绿屏上生成，再去背得到透明 PNG。
