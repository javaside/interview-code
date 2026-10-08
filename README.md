# interview-code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Java](https://img.shields.io/badge/Java-17+-blue.svg)](pom.xml)
[![Maven](https://img.shields.io/badge/Maven-multi--module-orange.svg)](pom.xml)

[interview-drill](https://xibaojun.com/drill) 题库的示例代码仓。**对应的题目均已上线：[xibaojun.com/drill](https://xibaojun.com/drill)**，每道题的示例类头部 Javadoc 标注了题卡 ID，可与线上题目一一对照。

## 结构映射

知识地图的映射关系（约定全文见 [docs/design.md](docs/design.md)）：

| interview-drill 题库 | 本项目 |
|---|---|
| 知识地图大类（content/ 一级目录，如 java、jvm） | Maven 模块（同名目录） |
| 知识块（content/java/string 等） | Java 包（com.interview.<大类>.<块名>） |
| 题卡（一题一卡，ULID.md） | 演示类（一题一类，主题 + Demo） |

当前模块状态：

- [x] **java** — 10 个知识块 × 5 题 = 50 个可运行演示类
- [ ] jvm / concurrency / mysql / network / os / distributed / spring / mq / rpc / architecture / agent — 待扩展

## 运行示例

要求 JDK 17+，零第三方依赖。

```bash
mvn compile    # 编译全部模块
```

每个演示类都有独立的 `main` 方法，直接运行即可在控制台看到题目相关现象：

```bash
# 命令行运行单个示例
java -cp java/target/classes com.interview.java.string.StringHashCodeDemo

# 或在 IDE 里直接运行任意 Demo 类
```

示例类约定：

1. 运行即可看到题目相关现象，输出用中文讲解；
2. Javadoc 头部三行：题目原文、题卡 ULID、块 ID——可回溯到 interview-drill 的 content 源文件与线上题目；
3. 要点口径与题库题卡正文一致；无法在当前 JDK 复现的题（如 JDK 7 HashMap 死循环）写讲解性演示。

## 包名对照（java 模块）

| 知识块 | 包 | 题数 |
|---|---|---|
| language-basics | com.interview.java.languagebasics | 5 |
| string | com.interview.java.string | 5 |
| generics | com.interview.java.generics | 5 |
| equals-hashcode | com.interview.java.equalshashcode | 5 |
| exceptions | com.interview.java.exceptions | 5 |
| collections-overview | com.interview.java.collections | 5 |
| arraylist | com.interview.java.arraylist | 5 |
| hashmap | com.interview.java.hashmap | 5 |
| concurrent-hashmap | com.interview.java.concurrenthashmap | 5 |
| reflection-proxy | com.interview.java.reflectionproxy | 5 |

## 贡献

欢迎提 Issue / Pull Request，约定见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 许可证

[MIT](LICENSE) © 2026 zxh
