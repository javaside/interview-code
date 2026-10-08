# interview-code 结构约定

本项目是 [interview-drill](../IdeaProjects/interview-drill) 题库的示例代码仓。核心映射关系：

| interview-drill | 本项目 |
|---|---|
| 知识地图大类（content/ 下的一级目录，如 java、jvm） | Maven 模块（同名目录） |
| 知识块（content/java/string 等，block.yml 的 name） | Java 包（com.interview.<大类>.<块名>） |
| 题卡（ULID.md，一题一卡） | 演示类（一题一类，类名 = 主题 + Demo） |

## 模块状态

- [x] java — content/java，10 块 × 5 题 = 50 个演示类
- [ ] jvm、concurrency、mysql、network、os、distributed、spring、mq、rpc、architecture、agent — 待添加

新加大类的步骤：父 pom `<modules>` 注册目录 → 建模块 pom（照抄 java 模块）→ 按下述约定写演示类。

## 演示类约定

1. 每类一个 `public static void main`，运行即可在控制台看到题目相关现象；输出用中文讲解。
2. 类 Javadoc 头部固定三行：题目原文（题卡 front matter 的 question）、题卡 ULID、块 ID（blockId），可回溯到 interview-drill 的 content 源文件。
3. 答案要点以注释或输出形式写在演示里，口径与题卡正文一致；正文分入门/进阶，演示类只做「现象呈现 + 面试口径」。
4. 无法在当前 JDK 复现的题（如 JDK7 HashMap 死循环）写讲解性演示：注释推演原理 + 演示能跑的部分。
5. 零第三方依赖，纯 JDK；编译基线 Java 17（与题卡 appliesTo: Java 17+ 一致）。

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

## 常用命令

```bash
mvn compile                          # 全量编译
mvn -pl java exec:java -Dexec.mainClass=com.interview.java.string.StringHashCodeDemo  # 跑单个演示（需 exec 插件，或直接 IDE 运行）
```
