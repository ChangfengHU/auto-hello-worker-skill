# hello-worker

调用 `https://hello-worker.hb67egcim4.workers.dev/`，返回 `Hello from Cloudflare Worker! 🚀`。

---

## 1. 直接执行 CLI

不需要安装 skill，一条命令直接调用：

```bash
bash <(curl -fsSL https://skill.vyibc.com/hello-worker.sh) --mode=hello
```

---

## 2. 安装为 Claude Code Skill

```bash
bash <(curl -fsSL 'https://skill.vyibc.com/install-hello-worker.sh')
```

安装后 skill 会写入：

- `~/.claude/skills/hello-worker/SKILL.md`
- `~/.claude/skills/hello-worker/scripts/run.sh`

### 安装完成后如何使用

对 Claude 说以下任意一句，skill 会自动触发：

- `调用 hello-worker`
- `hello-worker`
- `请求一下 hello worker 接口`
- `帮我测试 hello-worker`

Claude 会执行：

```bash
~/.claude/skills/hello-worker/scripts/run.sh --mode=hello
```

并把结果返回给你：

```
Hello from Cloudflare Worker! 🚀
```

---

## 3. 支持的调用模式

| 模式 | 说明 |
|------|------|
| `hello` | 调用 hello-worker endpoint，返回问候语 |

---

## 4. 发布

本地发布（需要在仓库目录下）：

```bash
./scripts/publish-skill.sh
```

从 GitHub `main` 远程发布：

```bash
bash <(curl -fsSL https://skill.vyibc.com/publish-hello-worker.sh)
```

---

## 5. 仓库结构

```text
README.md
scripts/
  hello-worker.sh              # CLI 直接执行入口
  publish-hello-worker.sh      # 远程一键发布
  publish-skill.sh             # 本地发布
  upload-file.sh               # R2 上传工具
skills/
  hello-worker/
    SKILL.md                   # Claude Code skill 定义
    scripts/run.sh             # 唯一核心执行逻辑
```

`scripts/hello-worker.sh` 和安装后的 `skills/hello-worker/scripts/run.sh` 来自同一份脚本。
