---
name: hello-worker
description: "当用户说"调用 hello-worker"、"hello-worker"、"请求 hello worker 接口"、"帮我测试 hello-worker"、"hello worker 返回什么" 时自动触发。调用公网 Cloudflare Worker，返回 Hello from Cloudflare Worker! 🚀。"
---

# Hello Worker

## 作用

调用 `https://hello-worker.hb67egcim4.workers.dev/`，返回 `Hello from Cloudflare Worker! 🚀`。

## 执行

```bash
~/.claude/skills/hello-worker/scripts/run.sh --mode=hello
```

## 参数

| 参数 | 必填 | 说明 |
|------|------|------|
| `--mode` | 是 | 固定传 `hello` |

## 预期输出

```
Hello from Cloudflare Worker! 🚀
```
