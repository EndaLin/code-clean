<h1 align="center">✨ code-clean：Java &amp; Go（Golang）代码整洁指南</h1>

<p align="center">
  <strong>支持 Java 与 Go（Golang）的 AI 编程 Skill：代码编写、代码重构与代码审查</strong>
</p>

<p align="center">
  先识别代码语言，再分别应用两套独立规范，让代码更清楚、可靠、容易维护
</p>

<p align="center">
  <img alt="Java Clean Code" src="https://img.shields.io/badge/Java-Clean%20Code-ED8B00?style=for-the-badge&amp;logo=openjdk&amp;logoColor=white">
  <img alt="Go Golang Clean Code" src="https://img.shields.io/badge/Go%20%7C%20Golang-Clean%20Code-00ADD8?style=for-the-badge&amp;logo=go&amp;logoColor=white">
  <img alt="AI Coding Skill" src="https://img.shields.io/badge/AI%20Coding-Skill-7C3AED?style=for-the-badge&amp;logo=sparkles&amp;logoColor=white">
</p>

<p align="center"><strong>当前支持：Java · Go · Golang</strong></p>

---

## 💡 它解决什么问题

很多代码“能跑”，却依然存在这些问题：名称看不懂、方法职责混乱、异常被吞、日志不可排查、并发任务无法退出，或者一次所谓的重构顺手改变了原有行为。

`code-clean` 为 AI 提供一套可执行的代码质量判断框架，让它知道：

- 什么是需要修复的真实问题，什么只是可选的风格建议。
- 如何在不破坏现有接口和行为的前提下改善代码。
- 如何先识别代码语言，再选择对应的独立资料，不把 Java 规则套给 Go，也不反向套用。
- 修改完成后应该验证什么，证据不足时不能声称已经可用。

> **一句话价值：** 减少“代码写完了，但难读、难改、难排查”的后续成本。

## 💎 核心价值

<table>
  <tr>
    <td width="25%" align="center">
      <strong>✍️ 写得清楚</strong><br><br>
      用准确命名、合理方法和清晰边界表达业务意图
    </td>
    <td width="25%" align="center">
      <strong>🔍 审得准确</strong><br><br>
      区分明确缺陷与个人偏好，给出位置、影响和最小修复
    </td>
    <td width="25%" align="center">
      <strong>🧹 改得安全</strong><br><br>
      重构时保护公开接口、数据格式和已有行为
    </td>
    <td width="25%" align="center">
      <strong>🛡️ 验得可靠</strong><br><br>
      根据风险执行测试与真实边界验证，不用猜测代替结论
    </td>
  </tr>
</table>

## 🧰 产品能力

| 能力 | 适用任务 | 产出 |
| --- | --- | --- |
| ✍️ 代码编写 | 新功能、公共接口、领域逻辑、基础组件 | 符合项目习惯且更容易理解的新代码 |
| 🧹 安全重构 | 长方法、重复逻辑、职责混乱、历史代码整理 | 保持行为不变的集中改动与验证结果 |
| 🔍 代码审查 | Pull Request、变更集、关键模块巡检 | 按严重程度排列的问题、证据与最小修复建议 |
| 🧯 错误治理 | 异常、错误码、日志、资源释放 | 可追踪、可恢复且不泄露敏感信息的失败路径 |
| ⚙️ 并发检查 | 线程、goroutine、锁、channel、任务取消 | 明确的所有权、退出条件、同步方式与竞态验证 |
| 🧪 测试改进 | 缺陷修复、边界场景、外部系统集成 | 能保护真实行为而非迎合实现细节的测试 |

## 🎯 适用场景

- 新增或修改代码，希望从一开始就保持清楚可靠。
- 审查 Java、Go 或混合技术栈的代码变更；混合仓库按文件或模块分别选择资料。
- 整理历史代码，但不能破坏现有接口和业务行为。
- 检查命名、注释、方法、错误处理、日志、并发或测试质量。
- 团队需要统一判断标准，避免代码审查陷入纯粹的个人风格争论。

以下任务通常不需要单独使用本 Skill：

- 只需要执行格式化工具，没有代码质量判断。
- 只修改文字、图片或与代码无关的内容。
- 用户明确要求保持原样，且任务中不存在正确性或维护性决策。

## 🗃️ 两套独立规范

> [!IMPORTANT]
> Java 与 Go 不是一套合并后的规则。两种语言各自拥有完整的规范目录和读取入口；处理某种语言时，不加载另一种语言的规则。

### ☕ Java 代码整洁资料

<p>
  <img alt="Java" src="https://img.shields.io/badge/Java-Clean%20Code-ED8B00?style=for-the-badge&amp;logo=openjdk&amp;logoColor=white">
  <img alt="Independent Java Rules" src="https://img.shields.io/badge/Java%20Rules-Independent-B45309?style=for-the-badge">
</p>

**规范范围：** Java 命名、方法、注释、格式、异常、日志、类设计、集合、并发、测试、数据库与安全边界。

| Java 主题 | 独立资料入口 |
| --- | --- |
| 命名、方法、注释、格式 | [`naming.md`](references/java/naming.md) · [`methods.md`](references/java/methods.md) · [`comments.md`](references/java/comments.md) · [`formatting.md`](references/java/formatting.md) |
| 异常、日志、类与测试 | [`exceptions-and-logging.md`](references/java/exceptions-and-logging.md) · [`classes-and-design.md`](references/java/classes-and-design.md) · [`testing.md`](references/java/testing.md) |
| 类型、集合、并发与数据边界 | [`language-and-data.md`](references/java/language-and-data.md) · [`collections-and-concurrency.md`](references/java/collections-and-concurrency.md) · [`database-security-architecture.md`](references/java/database-security-architecture.md) |

**适合处理：** Java 服务、Spring 项目、公共 API、集合与并发、异常与日志、数据库及安全边界。

```text
使用 $code-clean 审查这个 Java 服务，区分明确缺陷和可选建议，并给出最小修复。
```

### 🐹 Go 代码整洁资料

<p>
  <img alt="Go" src="https://img.shields.io/badge/Go-Idiomatic%20Code-00ADD8?style=for-the-badge&amp;logo=go&amp;logoColor=white">
  <img alt="Independent Go Rules" src="https://img.shields.io/badge/Go%20Rules-Independent-0891B2?style=for-the-badge">
</p>

**规范范围：** Go 格式、命名、注释、函数、方法、类型、接口、泛型、错误处理、并发与测试。

| Go 主题 | 独立资料入口 |
| --- | --- |
| 格式、命名与注释 | [`formatting-and-naming.md`](references/go/formatting-and-naming.md) · [`comments.md`](references/go/comments.md) |
| 函数、方法、类型、接口与泛型 | [`functions-types-and-interfaces.md`](references/go/functions-types-and-interfaces.md) |
| 错误、并发与测试 | [`errors.md`](references/go/errors.md) · [`concurrency.md`](references/go/concurrency.md) · [`testing.md`](references/go/testing.md) |

**适合处理：** Go package、服务端程序、公开接口、错误链、goroutine 生命周期、channel、锁、竞态与测试。

```text
使用 $code-clean 重构这个 Go 包，保持公开接口不变，重点检查错误处理和 goroutine 生命周期。
```

## 🚀 使用方式

将仓库放入支持 `SKILL.md` 的 AI 编程工具技能目录，并确保目录根部直接包含 [`SKILL.md`](SKILL.md)。随后通过 `$code-clean` 调用，工具会先识别目标代码语言，再进入 Java 或 Go 的独立资料目录。

入口不会预先合并或加载所有规范。它先根据目标文件、语法、导入和构建信息定位语言；混合仓库按文件或模块分别路由，无法可靠识别时会明确假设或请求确认。

### 通用调用格式

```text
使用 $code-clean 实现这个功能，遵循仓库已有规范，并运行与改动相关的测试。
```

## 🧠 它如何工作

```text
根据文件、语法、导入和构建信息识别语言
├── Java ──→ 只读取 references/java/
└── Go   ──→ 只读取 references/go/
                    ↓
          理解现有约定与兼容边界
                    ↓
            编写、重构或审查代码
                    ↓
          执行验证并报告实际证据
```

它不会用固定行数、方法长度或个人喜好机械判定代码好坏。仓库规范、正确性、安全性、兼容性和当前语言版本始终拥有更高优先级。

## 🗂️ 仓库结构

```text
code-clean/
├── SKILL.md                  # 能力入口、边界和规则路由
├── agents/openai.yaml        # 展示与调用元数据
└── references/
    ├── java/                 # 完整、独立的 Java 资料
    └── go/                   # 完整、独立的 Go 资料
```

## 📚 官方规范依据

### Java

- Robert C. Martin 的 [*Clean Code: A Handbook of Agile Software Craftsmanship*](https://www.pearson.com/en-us/subject-catalog/p/clean-code-a-handbook-of-agile-software-craftsmanship-2nd-edition/P200000013239/9780135398579)。
- 阿里巴巴集团公开发布的《Java 开发手册（黄山版，1.7.1）》。
- [Java 官方文档](https://docs.oracle.com/en/java/javase/)与目标项目实际采用的 Java 版本。

### Go

- Go 官方的 [Effective Go](https://go.dev/doc/effective_go)。
- Go 官方的 [Go Doc Comments](https://go.dev/doc/comment) 与 [Go Code Review Comments](https://go.dev/wiki/CodeReviewComments)。
- [Go 官方文档](https://go.dev/doc/)与目标项目实际采用的 Go 版本。

Java 与 Go 规范独立维护。实现与审查时，目标仓库约定、正确性要求和当前语言版本优先。

## 🌍 其他语言——欢迎提交 MR

目前内置 Java 和 Go（Golang）两种语言。欢迎通过 MR（GitHub Pull Request）增加 Python、Rust、TypeScript、C# 等语言；每种新语言都应建立完整、独立的 `references/<language>/` 目录，并在 `SKILL.md` 中增加自己的识别条件和按主题入口。

跨语言共用的执行流程保留在 `SKILL.md`，具体编码规则不放到公共目录，也不从其他语言目录借用。

## 📄 License

本仓库采用 [Apache License 2.0](LICENSE)。
