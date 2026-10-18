# 贡献指南

欢迎提交个人介绍、挑战成果、实验和文档改进。一次 PR 尽量只完成一件事，方便 Review。

## 第一次提交：个人介绍

### 在网页上完成

1. 点击仓库右上角 Fork，创建自己的副本。
2. 在副本中创建工作分支，例如 `intro/your-username`。
3. 打开 `members/example.md`，复制内容，新建 `members/<你的 GitHub 用户名>.md`。
4. 填写愿意公开的信息，不要修改示例或其他同学的介绍。
5. 提交修改，点击 Compare & pull request。
6. 确认目标是 `codepaintstudio/playground` 的 `main`，来源是你 Fork 中的工作分支，填写 PR 模板并提交。
7. 收到反馈后，在同一分支继续修改，PR 会随之更新。
8. 我们审核并合并后，向提交 PR 的 GitHub 账号发送组织邀请；使用该账号接受即可。

### 在本地完成

将下面的 `YOUR_USERNAME` 替换为自己的 GitHub 用户名。先在 GitHub 上完成 Fork，再执行：

```bash
git clone https://github.com/YOUR_USERNAME/playground.git
cd playground
git remote add upstream https://github.com/codepaintstudio/playground.git
git switch -c intro/YOUR_USERNAME
```

复制 `members/example.md` 为自己的介绍文件并编辑，然后提交：

```bash
git add members/YOUR_USERNAME.md
git commit -m "docs: add YOUR_USERNAME introduction"
git push -u origin intro/YOUR_USERNAME
```

打开自己 Fork 的 GitHub 页面创建 PR。新任务开始前，先同步主分支，再创建新的工作分支：

```bash
git switch main
git fetch upstream
git merge --ff-only upstream/main
git push origin main
git switch -c challenge/your-task
```

如果同步报错，先保留当前修改，在 Issue 中说明报错与分支情况，请负责人协助。

## 挑战与实验

1. 查看 [挑战列表](challenges/README.md)，在已有任务 Issue 下留言认领；没有任务 Issue 时使用“挑战认领”模板新建一个。
2. 与负责人确认目标和验收要求后开始。自由实验可使用“实验提案”模板先讨论。
3. 在 `experiments/<你的 GitHub 用户名>/<项目名>/` 下提交成果。项目名建议使用小写英文和连字符。
4. 每个项目提供 README，包含目标、运行或查看方式、结果、验证方法、已知限制和引用来源。可参考 [实验示例](experiments/example/README.md)。
5. 提交 PR 并关联 Issue。多人完成同一挑战时使用各自的成果目录，避免覆盖。

文档可以直接提交 Markdown；代码要提供可执行步骤；设计和 AIGC 成果要提供可查看的预览、过程说明及来源。不要提交依赖目录、构建产物、大型模型或数据集。

## PR 怎么写

标题示例：

- `docs: add your-username introduction`
- `feat: complete frontend profile challenge`
- `docs: clarify challenge setup steps`

使用仓库提供的 PR 模板，说明修改、关联任务和验证结果。独立任务可写 `Closes #编号`；多人共用的挑战 Issue 使用 `Refs #编号`，不要在个人 PR 中关闭整个任务。

还没完成但需要帮助时，可以先开 Draft PR，具体写出卡在哪里。

## Review 与合并

- 负责人查看提交范围、验收项和成果说明，必要时提出修改意见。
- 收到意见后，在原分支修改并回复处理结果，不需要重新开 PR。
- 被指出问题是练习的一部分。遇到不同意见时，说明依据和取舍。
- 个人介绍 PR 审核并合并后，我们向 PR 提交者的 GitHub 账号发送组织邀请。请使用准备加入组织的账号提交 PR，并确保介绍中的用户名一致。

## 提交前检查

- 只修改本次任务相关内容，没有覆盖其他人的成果。
- 按任务验收要求检查过，并在 PR 中写出具体结果。
- README 中的命令、链接和预览可用。
- 没有密码、Token、真实用户数据或不愿公开的个人信息。
- 引用第三方内容时写明来源与许可；使用 AI 时写明用途、修改与验证情况。

## 维护者操作

个人介绍 PR 审核并合并后，向 PR 提交者的 GitHub 账号发送组织邀请。挑战与自由实验是可选练习，不作为邀请条件。

这一步由 [.github/workflows/invite-contributor.yml](.github/workflows/invite-contributor.yml) 自动完成，规则是：

- 触发时机：本仓库的 PR 被合并时（对来自 fork 的 PR 同样生效），取 PR 作者账号为邀请对象。
- 邀请范围：只有 PR 改动了 `members/` 下的个人介绍文件才会邀请。`members/README.md` 与 `members/example.md` 是仓库脚手架，不算个人介绍。因此挑战与自由实验的 PR 合并后不会发邀请，与「个人介绍 PR 才发邀请」的规则一致。
- 例外：手动运行 workflow 不受上面的范围限制，用于补发遗漏的邀请。
- 已是组织成员：只补 `all-members` team 归属，不重复发邀请。
- 已有待接受的邀请：只补 team 归属，不重复发邀请。
- 不是组织成员：发送组织邀请，并把 `all-members` team 一并写进邀请，对方接受后自动进入该 team。
- 机器人账号（如 `dependabot[bot]`）会跳过。

### 一次性配置

1. 在组织里创建 `all-members` team（若尚未创建），用于容纳全部成员。
2. 准备一个有组织管理权限的 Token，并要求它是组织 Owner，才能邀请非成员：
   - Classic PAT：勾选 `admin:org`。
   - Fine-grained PAT：Organization permissions 中 `Members` 设为 `Read and write`。
3. 把 Token 存为 Secret，名称为 `ORG_ADMIN_TOKEN`。推荐存成**组织级 Secret** 并授权本仓库访问，这样和 [codepaintstudio/.github](https://github.com/codepaintstudio/.github) 的定时同步共用一份。
4. 该 workflow 使用 `pull_request_target`，必须存在于默认分支上才会对合并事件生效——也就是说，本文件合并进 `main` 之后才开始工作。

### 手动补发

邀请失败或遗漏时，到 Actions 里手动运行 **Invite contributor**：

- `username`：要邀请的 GitHub 用户名。
- `dry_run` 设为 `true` 可以只查看当前成员状态、不做任何修改。

组织成员与 `all-members` team 的最终一致性由 [codepaintstudio/.github](https://github.com/codepaintstudio/.github) 的每日同步任务兜底；本 workflow 只负责在合并的那一刻尽快发出邀请。因此**邀请与 team 同步的逻辑放在本仓库**（只有本仓库能收到这里的 PR 合并事件），而组织级的批量对账放在 `.github` 仓库。
