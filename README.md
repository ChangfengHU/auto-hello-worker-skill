        # hello-worker

        `hello-worker` 用来封装 `https://hello-worker.hb67egcim4.workers.dev/` 这个能力，对外提供两个主要入口：

- 安装一个真正的 skill 到 agent 环境
- 直接执行 CLI 调用这个 HTTP 接口

Wrap the hello-worker Cloudflare Worker as a skill+cli project. Returns 'Hello from Cloudflare Worker! 🚀'.

        ## 1. 直接执行 CLI

```bash
bash <(curl -fsSL https://skill.vyibc.com/hello-worker.sh) --mode=hello
```

        ## 2. 安装 skill

        ```bash
        bash <(curl -fsSL 'https://skill.vyibc.com/install-hello-worker.sh?ts=...')
        ```

        这个命令会把 `hello-worker` 安装到目标 skill 目录，例如：

- `~/.codex/skills/hello-worker`
- `~/.claude/skills/hello-worker`
- `~/.cursor/skills/hello-worker`

安装完成后，skill 内会包含：

- `SKILL.md`
- `scripts/run.sh`

## 3. 支持的调用模式

        - `hello`: Call the hello-worker endpoint and return the greeting.



        ## 4. 调用示例

        ### Basic call

```bash
bash <(curl -fsSL https://skill.vyibc.com/hello-worker.sh) --mode=hello
```

        ## 5. 发布

        本地发布：

        ```bash
        ./scripts/publish-skill.sh
        ```

        从 GitHub `main` 远程发布：

        ```bash
        bash <(curl -fsSL https://skill.vyibc.com/publish-hello-worker.sh)
        ```

        ## 6. 核心执行入口

        ```text
        skills/hello-worker/scripts/run.sh
        ```
