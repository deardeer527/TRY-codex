# TRY-codex 协作约定

本目录是 DeepSeek Harness 的会话工作区，对应 GitHub 仓库
`deardeer527/TRY-codex`。你产出的所有代码改动都必须托管进该仓库。

## 每轮任务收尾（必须执行）

1. `git status --short` 检查改动，确认没有密钥、`.env`、大文件、构建产物混入。
2. 跑与改动相关的测试或构建（如果仓库里有）。
3. `git add -A && git commit -m "<type>: <summary>"`
   - type 用 feat / fix / docs / refactor / test / chore
4. `git push origin HEAD`；当前分支没有 upstream 时用 `git push -u origin <branch>`。
5. 在最终回复里写清：提交哈希、分支名、推送结果。推送失败必须报告错误原文，
   不允许静默跳过。

## 规则

- 禁止 `git push --force`、禁止改写已推送历史、禁止 `git reset --hard` 丢弃用户改动。
- 用户没有特别要求评审流程时，直接推送 `main`；要求时新建 `feat/<简述>` 分支再推。
- 遇到冲突、认证失败（401/403）、网络失败：停止操作，说明原因并交给用户处理，
  不要反复重试、不要改变仓库配置来"绕过"。
- 提交信息中英文均可，但本仓库保持一致。
- 不提交 `.env`、`*.pem`、`node_modules/`、`dist/`、`build/`、`.DS_Store` 等，
  以 `.gitignore` 为准。
