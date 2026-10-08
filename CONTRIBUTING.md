# 贡献指南

感谢关注 interview-code！欢迎通过 Issue 和 Pull Request 参与贡献。

## 项目约定

动手前请先读 [docs/design.md](docs/design.md)，核心映射关系：

- 知识地图大类 = Maven 模块（如 `java/`）
- 知识块 = Java 包（如 `com.interview.java.string`）
- 题卡 = 演示类（一题一类，主题 + `Demo` 后缀）

## 新增演示类

1. 每个演示类一个 `public static void main`，运行即可在控制台看到题目相关现象，输出用中文讲解；
2. 类 Javadoc 头部固定三行：题目原文、题卡 ULID、块 ID；
3. 要点口径与题库（[interview-drill](https://xibaojun.com/drill)）题卡正文保持一致；
4. 纯 JDK 实现，不引入第三方依赖；编译基线 Java 17；
5. 无法在当前 JDK 复现的题写讲解性演示（注释推演原理 + 演示能跑的部分）。

## 提交前检查

```bash
mvn compile    # 必须全绿
# 新增的演示类请在本地跑一遍 main，确认输出符合预期
```

## 提交规范

- Conventional Commits，中文描述，如 `feat(hashmap): 新增 JDK7 死循环讲解性演示`；
- 一个 PR 聚焦一件事（一个知识块或一个主题）；
- PR 描述里写清楚对应哪道线上题目（题卡 ULID）。

## Issue

- 发现示例代码与题库口径不一致、编译或运行报错，欢迎提 Issue；
- 请附上：演示类全名、复现命令、实际输出、期望输出。
