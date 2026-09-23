# 学习清单

> 个人笔记仓库 —— 记录软件技术专业实习期间的学习计划、命令速查与踩坑记录。
> 当前阶段：**2026-09-21 ~ 2026-09-27（第 4 周）· GitHub 入门与协作**

## 仓库说明

| 项目 | 内容 |
| --- | --- |
| 仓库地址 | https://github.com/microshatter/personal-note |
| 用途 | 存放学习清单、Git 命令速查、问题记录 |
| 主分支 | `main` |
| 更新方式 | 每条学习记录一次提交，提交信息遵循下方规范 |

## 进度总览

| # | 学习任务 | 状态 |
| --- | --- | --- |
| 1 | GitHub 入门：注册、安装 Git、配置身份、绑定 SSH | 未完成 |
| 2 | 仓库完整闭环：clone → add → commit → push | 进行中 |
| 3 | 分支管理与版本控制 | 未完成 |
| 4 | Fork 与 Pull Request（了解即可） | 了解中 |
| 5 | Issues 任务追踪与 GitHub 高级搜索 | 未完成 |
| 6 | GitHub Actions 自动化与 Pages 静态托管 | 已完成 |
| 7 | 录音卡相关开源项目研读 | 未完成 |

## 详细清单

### 1. GitHub 入门

- [ ] 访问 GitHub 官网注册账号，完善个人资料
- [ ] 安装 Git 命令行工具（Windows 使用 Git Bash）
- [ ] 配置全局身份
  ```bash
  git config --global user.name "用户名"
  git config --global user.email "邮箱"
  git config --global --list   # 校验配置
  ```
- [ ] 生成并绑定 SSH 密钥，实现免密通信
  ```bash
  ssh-keygen -t ed25519 -C "邮箱"      # 一路回车，生成密钥对
  cat ~/.ssh/id_ed25519.pub            # 复制公钥到 GitHub → Settings → SSH keys
  ssh -T git@github.com                # 出现 successfully authenticated 即成功
  ```
- [ ] 完成 GitHub 官方 "Hello World" 交互式教程（约 10 分钟）
- [ ] 可选：安装 GitHub Desktop 或 VS Code 降低命令行门槛

### 2. 仓库创建、克隆、提交、推送闭环

- [ ] 网页端创建仓库，勾选 *Add a README file* 初始化，理解 Public / Private 区别
- [ ] 跑通核心命令链
  ```bash
  git clone https://github.com/microshatter/personal-note.git
  git add .                                  # 暂存变更
  git commit -m "docs: 添加学习清单"          # 本地提交
  git push                                   # 推送至远程
  ```
- [ ] 配置 `.gitignore`，排除日志、缓存、环境变量等文件
- [ ] 用 `git status` 查看工作区状态，用 `git log` 查看提交历史
- [x] **创建个人笔记仓库 `personal-note`，用 Markdown 写一份学习清单并提交** ← 本文件即交付物

### 3. 分支管理与版本控制

- [ ] 理解分支作用：隔离开发，避免直接影响 `main` 主干
- [ ] 练习分支命令
  ```bash
  git branch                     # 查看分支
  git checkout -b feature/xxx    # 创建并切换
  git merge feature/xxx          # 合并回 main
  git branch -d feature/xxx      # 删除已合并分支
  ```
- [ ] 遵守规范：从 `main` 创建 `feature/xxx` 特性分支开发，禁止直接改主干
- [ ] 学习版本回退：`git reset`（强制回退，仅限未推送分支）与 `git revert`（反向提交，适合多人协作）
- [ ] 练习：创建 `feature/update-readme` 分支，修改 README 后合并回 `main`

### 4. Fork 与 Pull Request（了解即可）

- [ ] 理解 Fork：复刻他人开源项目到个人仓库，作为自己的副本
- [ ] 了解 PR 流程：推送分支 → New Pull Request → 选择源/目标分支 → 填写描述 → 指定 Reviewers → 等待合并
- [ ] 了解代码审查：查看 Diff、添加评论、根据反馈继续修改分支
- [ ] 了解同步上游
  ```bash
  git remote add upstream 原仓库URL
  git fetch upstream
  git merge upstream/main
  ```

### 5. Issues 与高效搜索

- [ ] 学习 Issues：Bug 反馈、功能建议、任务追踪，支持 Label / Assignee / 模板
- [ ] 掌握搜索语法：`stars:>1000`、`language:python`、`label:"good first issue"`
- [ ] 学习用 Projects 看板视图管理工作流
- [ ] 记住快捷键：`t` 搜索文件、`l` 跳转行号、`b` 切换分支、`?` 查看全部快捷键
- [ ] 用高级搜索找到不少于 2 个录音卡相关项目并 Star 收藏

### 6. 自动化部署与静态网站托管

- [x] 学习 GitHub Actions：在 `.github/workflows/` 下编写 YAML，实现 CI/CD
- [x] 学习 GitHub Pages：在仓库 Settings 中配置，免费托管页面
- [ ] 了解 Dependabot：自动检测依赖漏洞并生成更新 PR
- [ ] 了解 GitHub Copilot：AI 编程助手
- [x] 交付物：为 `Earthquake-EEW-Godot` 配置 Godot 导出/发布工作流；个人页面仓库 `microshatter.github.io`

### 7. 录音卡相关开源项目研读

- [ ] https://github.com/uui77/NextProto
- [ ] https://github.com/sudomarcma/kardo
- [ ] https://github.com/nextproto1024/ai-recorder-card-open-protocol
- [ ] https://github.com/patdelphi/pat-funasr
- [ ] 本周先学习了解，后续阶段再实际使用

## Git 常用命令速查

| 命令 | 作用 |
| --- | --- |
| `git config --global user.name "x"` | 配置全局用户名 |
| `git clone <url>` | 克隆远程仓库到本地 |
| `git status` | 查看工作区状态 |
| `git add .` | 暂存全部变更 |
| `git commit -m "msg"` | 提交到本地仓库 |
| `git push` | 推送本地提交到远程 |
| `git pull` | 拉取并合并远程更新 |
| `git log --oneline` | 查看简洁提交历史 |
| `git branch` / `checkout -b` | 查看 / 创建并切换分支 |
| `git merge <branch>` | 合并指定分支到当前分支 |
| `git reset` / `git revert` | 版本回退 / 反向提交 |
| `git remote -v` | 查看远程仓库地址 |
| `ssh -T git@github.com` | 验证 SSH 免密配置 |

## 提交信息规范

采用 `<类型>: <描述>` 格式，一行说清做了什么：

| 类型 | 含义 |
| --- | --- |
| `docs` | 文档 / 笔记变更 |
| `feat` | 新增功能或内容 |
| `fix` | 修正错误 |
| `chore` | 杂项（配置、依赖等） |

示例：`docs: 补充第 4 周 Git 分支学习笔记`

## 参考项目

除本周需研读的录音卡项目外，已 Fork 的参考项目：

- https://github.com/microshatter/astrbot_plugin_disaster_warning_eng
- https://github.com/microshatter/BotPlaysZenithClicker
- https://github.com/microshatter/nullpomino

## 下一步

1. 完成 SSH 绑定与 "Hello World" 教程，跑通第一次 `push`
2. 建立 `feature/update-readme` 分支练习合并流程
3. 用高级搜索补齐录音卡项目调研并 Star
4. 为每个任务补充对应的截图或链接，回填阶段任务清单的「交付物」
