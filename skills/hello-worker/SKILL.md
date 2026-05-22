        ---
        name: hello-worker
        description: "Wrap the hello-worker Cloudflare Worker as a skill+cli project. Returns 'Hello from Cloudflare Worker! 🚀'."
        ---

        # Hello Worker

        ## 作用

        当用户希望把 `hello-worker` 作为一个真正的 skill 安装到 agent 环境里，并通过统一参数调用它时，使用这个 skill。

        ## 安装

        ```bash
        bash <(curl -fsSL 'https://skill.vyibc.com/install-hello-worker.sh?ts=...')
        ```

        ## 核心执行入口

        ```text
        skills/hello-worker/scripts/run.sh
        ```

        安装后的 skill 和对外发布的 CLI 都来自这一个脚本。

        ## 直接执行

```bash
bash <(curl -fsSL https://skill.vyibc.com/hello-worker.sh) --mode=hello
```
