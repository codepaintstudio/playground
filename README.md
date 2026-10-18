# CodePaint Playground

CP 码绘新人入门、技术探索与开源协作实践仓库。

欢迎来到练习场。这里可以练习 Git 与 GitHub 协作、完成入门挑战，也可以放下自己的小实验。第一次提交不需要做出复杂项目：先完成一份个人介绍，走通提交与 Review 的流程。

## 从这里开始

1. 阅读 [贡献指南](CONTRIBUTING.md)，Fork 本仓库。
2. 复制 [个人介绍示例](members/example.md)，新建 `members/<你的 GitHub 用户名>.md`。
3. 提交一个个人介绍 PR，按照模板说明做了什么。
4. 我们审核并合并 PR 后，向提交 PR 的 GitHub 账号发送组织邀请。
5. 使用同一账号接受邀请，加入 CodePaint。

[入门挑战](challenges/README.md)和自由实验可以按兴趣参与，不是获得组织邀请的前置要求。

## 目录

```text
playground/
├── README.md
├── CONTRIBUTING.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── workflows/
├── members/
│   ├── README.md
│   └── example.md
├── challenges/
│   ├── README.md
│   ├── frontend/
│   ├── backend/
│   ├── ai/
│   └── design/
└── experiments/
    ├── README.md
    └── example/
```

| 区域 | 用途 |
| --- | --- |
| [members](members/README.md) | 个人介绍与学习方向 |
| [challenges](challenges/README.md) | 前端、后端、AI、设计方向的入门任务与验收要求 |
| [experiments](experiments/README.md) | 挑战成果、自由探索和小型原型 |
| [Issues](https://github.com/codepaintstudio/playground/issues) | 认领任务、提问、讨论想法和报告问题 |

## 加入组织

流程：**Fork → 提交个人介绍 PR → 我们审核并合并 → 向该 GitHub 账号发送邀请 → 接受邀请。**

请使用准备加入组织的 GitHub 账号提交 PR，个人介绍中的用户名也填写该账号。我们以 PR 提交者的账号为邀请对象。

个人介绍 PR 合并后由 [邀请流程](.github/workflows/invite-contributor.yml) 自动执行：如果作者还不是组织成员，会立即发送组织邀请并预先加入 `all-members` team。接受邀请后即成为组织成员，同时出现在所有成员名单里。只有改动了 `members/` 下个人介绍文件的 PR 才会触发，挑战与自由实验的 PR 不在此列。如果长时间没有收到邀请邮件，请到 GitHub 的 [组织邀请页面](https://github.com/account/organizations) 查看，或在 Issue 中留言请负责人手动补发。

## 参与约定

- 可以提问，可以犯错。描述你试过什么，比只说“不会”更容易获得帮助。
- 可以使用 AI 辅助，但要能解释自己的提交，并写明工具用途与亲自验证的部分。
- 公开内容只填写愿意公开的信息；不用提交学号、手机号、住址或私有文件。
- 尊重他人的作品与时间。引用代码、图片、数据或素材时标明来源与使用许可。
- 优先做一个能说明白、能验证的小成果，再逐步扩展。
