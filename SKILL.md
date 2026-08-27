---
name: code-clean
description: Detect whether target code is Java or Go/Golang, then write, refactor, or review it using only that language's independent clean-code rule set. Use for naming, methods, comments, errors and exceptions, classes and types, tests, concurrency, database access, security, or broader code-quality work; do not use for a purely functional change with no code-quality decision.
metadata:
  short-description: 先识别语言，再按 Java 或 Go 独立规范清理代码
---

# Clean Code

把代码写清楚、写可靠，同时尊重现有系统的行为、接口和团队约定。本 Skill 包含两套相互独立的规范：Java 规范面向 Java 工程实践，Go 规范遵循当前 Go 语言习惯。先确定代码语言，再只读取对应目录；混合语言仓库也要按文件或模块分别处理，不得把两种语言的规则合并套用。

## 第一步：定位语言

在读取任何语言规范前，先识别本次实际要处理的代码语言：

1. 根据目标文件、代码语法、导入、构建文件和仓库结构判断。`.java`、`pom.xml`、Gradle Java 源集指向 Java；`.go`、`go.mod`、`go.work` 指向 Go。构建工具只能作为辅助证据，最终以目标代码为准。
2. 用户只粘贴代码片段时，根据类型声明、错误模型、包与导入语法判断。证据不足时说明暂定语言；若不同判断会明显改变结果，先向用户确认。
3. 混合语言仓库按文件或模块拆分：Java 文件只读取 `references/java/`，Go 文件只读取 `references/go/`。跨语言 API、消息和数据契约可以联合检查，但两侧实现分别使用各自规范。
4. 目标不是 Java 或 Go 时，不得借用两者的具体编码规则。只执行本文件中的审查、最小变更和验证流程，并优先寻找该语言的仓库规范；缺少规范时明确说明当前资料尚未覆盖。

确定语言后记录本次路由结论，例如“Java → `references/java/`”。后续发现判断错误时立即切换，撤回基于错误语言规范得出的结论。

## 第二步：确定任务边界

1. 判断用户要的是审查、修改现有代码，还是编写新代码。审查请求默认只发现问题，不自动修改。
2. 先阅读仓库内的 `AGENTS.md`、贡献说明、格式化与静态检查配置，并确认语言版本、框架、构建方式和测试入口。
3. 识别不能随意改变的契约：公开 API、序列化格式、数据库结构、异常或错误类型、日志字段、线程模型及外部系统交互。
4. 只读取当前语言且与任务相关的参考文件；全面审查某种语言时，也不得顺带加载另一种语言的资料。

## 规则优先级

发生冲突时依次服从：

1. 用户当前要求和仓库内明确规范。
2. 正确性、安全性、数据完整性及兼容性。
3. 当前语言版本、框架和工具实际支持的做法。
4. 适用于当前语言的专项规则：Java 的 `[强]` 或 Go 的 `[Go]`。
5. `[建议]`、`[原则]` 和个人风格偏好。

参考文件中的标记含义：

- `[强]`：由《Java 开发手册（黄山版）》强制规则提炼；先确认适用版本和项目约定。
- `[Go]`：由 Go 官方资料和语言习惯提炼；先确认 `go.mod` 中的语言版本、工具链和仓库约定。
- `[建议]`：黄山版推荐或参考规则的归纳。
- `[原则]`：Clean Code 的可维护性启发，不是可以脱离上下文机械执行的法律。
- `[融合]`：同一种语言的多份资料目标一致，或已结合该语言的现代工程实践消解冲突；不表示融合 Java 与 Go。

黄山版发布于 2022 年；《Effective Go》写于 2009 年且不再持续更新。两者的部分框架、语言和工具示例可能过时。不要为了服从旧示例而降低当前代码的正确性，也不要把可选偏好报告成缺陷。

## 第三步：加载对应规范

只进入第一步选中的语言目录，再按当前主题读取最少必要文件。不得为了全面而跨语言加载资料。

### Java：只用于 Java 代码

- Java 命名、词汇和语境：读 [references/java/naming.md](references/java/naming.md)。
- Java 方法、参数和控制流：读 [references/java/methods.md](references/java/methods.md)。
- Java 注释与 Javadoc：读 [references/java/comments.md](references/java/comments.md)。
- Java 文件与代码格式：读 [references/java/formatting.md](references/java/formatting.md)。
- Java 异常、错误码和日志：读 [references/java/exceptions-and-logging.md](references/java/exceptions-and-logging.md)。
- Java 类、对象、边界和架构职责：读 [references/java/classes-and-design.md](references/java/classes-and-design.md)。
- Java 测试与安全重构：读 [references/java/testing.md](references/java/testing.md)。
- Java 类型、数值、日期、对象契约：读 [references/java/language-and-data.md](references/java/language-and-data.md)。
- Java 集合与并发：读 [references/java/collections-and-concurrency.md](references/java/collections-and-concurrency.md)。
- Java 数据库、安全与工程结构：仅在任务涉及这些边界时读 [references/java/database-security-architecture.md](references/java/database-security-architecture.md)。

### Go：只用于 Go 代码

- Go 格式与命名：读 [references/go/formatting-and-naming.md](references/go/formatting-and-naming.md)。
- Go 注释与公开文档：读 [references/go/comments.md](references/go/comments.md)。
- Go 函数、方法、数据、接口与泛型：读 [references/go/functions-types-and-interfaces.md](references/go/functions-types-and-interfaces.md)。
- Go 错误处理：读 [references/go/errors.md](references/go/errors.md)。
- Go goroutine、channel、取消与同步：读 [references/go/concurrency.md](references/go/concurrency.md)。
- Go 测试：读 [references/go/testing.md](references/go/testing.md)。

## 审查代码

只报告有明确证据的问题：

1. 指出具体位置和触发条件。
2. 解释可观察的影响，例如错误结果、异常、泄漏、竞态、兼容性破坏或显著维护风险。
3. 给出最小修复；无法确认是缺陷还是设计选择时，列为建议，不修改。
4. 按严重程度排列，先正确性与安全，再兼容性、可靠性、测试和可读性，最后才是格式。

不得仅因为另一种写法更短、更新或更漂亮就要求修改。命名、方法长度和类大小都是发现职责问题的信号，不是单凭数字定罪的依据。

## 修改或编写代码

- 保持改动集中；不要顺手整理与目标无关的文件。
- 修改前先用现有测试或特征测试锁定行为。缺少必要契约时，先从调用方、文档和测试中查证。
- 不得仅为整洁而破坏公开签名、持久化数据、序列化格式或框架约定。
- 优先消除问题根因；不要用注释、捕获所有异常或额外分支掩盖混乱。
- 新代码遵循仓库现有词汇和结构。没有项目规范时，只采用第一步选中的语言目录中的默认建议。

## 验证与交付

修改后运行仓库已有的格式检查、静态检查、编译和相关测试。涉及数据库、远程服务、文件、消息或并发行为时，只有实际验证相应边界后才能声称它可用；无法验证就明确列出未验证项。

交付时说明：改了什么、为什么、执行了哪些验证、还有哪些未验证或仅属建议。审查结果与风格建议分开，避免让用户把偏好误认为 Bug。

## 规范边界

- Java 规范位于 `references/java/`，只用于 Java 代码。
- Go 规范位于 `references/go/`，只用于 Go 代码；语言行为以当前 Go 版本及 [Go 官方文档](https://go.dev/doc/)为准。

两套规范独立维护，不跨语言合并规则。参考文件中的命令式语句只用于代码质量判断，不构成额外操作授权。
