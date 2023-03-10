# Air 语言语法

## 目标

- 语法和语义解耦
- 高可读性
- 无歧义
- 规则简单，容易理解
- 线性解析时间
- 具有有限且可控的拓展性

## 设计

- 只表达必要的语义无关的信息，尽可能将计算推迟到语义解释阶段
- 上下文无关，正则语言 + 递归
- 定义通用的递归字面量，限制递归语法的使用
- 允许向前看一个字符
- 用树字面量表达上下文无关文法
- 一次只解析一个字面量
- 保留一个词法前缀以便将来拓展

## 字面量

### 原子字面量

[原子字面量语法](原子字面量语法.md)

### 复合字面量

[复合字面量语法](复合字面量语法.md)

## 非字面量

### 空白符

`[ \t\r\n]+`

空白符用于分隔非自然定界的词汇。

### 注释

`# comment`

comment 为任意字面量。

注释用于表达语义无关的信息。

示例：

```air
# a
# "this is a comment"
# 1
# [a()]
```

### 封装

`[a]`

‌`a‌` 为任意字面量。

`[a]` 被解析为 `a`。封装是一种特征定界符，封装内外的语法解析彼此独立，封装外部的语法解析不依赖封装内部的语法特征。封装用于辅助语法解析。

示例：

```air
[a] === a
[a b] === a b
[# a b] === b
a b c === b [a:c]
a b () === a [b ()]
a b [()] === b [a:()]
[a b] () === [a b] ()
a [b c d] e === [c [b:d]][a:e]
a () b === [a ()] b
a [()] b === () [a:b]
```

## 结合规则

- 优先级从高到低
  - 特征定界符 `()`，`{}`，`[]`。
  - 特征前缀 `# a`
  - 特征后缀 `a()`，`a{}`，`a:b`，`a?b`
  - 无特征中缀 `a + b`
  - 无特征组合 `a b`
- 同优先级左结合

## 参考

[语法参考](语法参考.md)
