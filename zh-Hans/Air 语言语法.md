# Air 语言语法

## 目标

- 语法和语义解耦
- 强表达能力
- 高可读性
- 无歧义
- 规则简单，容易理解
- 线性解析时间
- 具有有限且可控的拓展性

## 设计

- 只表达必要的语义无关的信息，尽可能将计算推迟到语义解释阶段
- 使用调用和解决表达任何语义
- 提供上下文语法，根据上下文切换解析规则
- 提供不结合语法，用于自定义语法
- 提供结构化的注释语法

## 空白符

空白符是由空格，制表符，换行符，回车符序列组成的文本。

空白符用于分隔词汇。

## 注释

`_(a)`

注释内容在解析时丢弃。注释内的语法比较宽松，只要求字符串和符号符合语法，定界符匹配即可。

```air
_("comment")

_(."
| multiline comment 1
+ multiline comment 2
|")

_(; f [1, 2, 3])
```

## 常规字符

ASCII 码中所有常规字符，从空格（` `）（32，含）到 `~`（126，含）。

- 字母（`a-zA-Z`）
- 数字（`0-9`）
- 标点（`` `~!@#$%^&*()_+-=[]{}\|;:'",.<>/? ``）
- 空格（` `）

## 符号

符号是由常规字符组成的字符序列。

## 定界符

定界符是用于确定词汇的边界的符号。

- ` `
- `,`
- `(`，`)`
- `[`，`]`
- `{`，`}`
- `'`
- `"`

## 符号形式

符号形式是由不包含定界符的符号构成的语法形式。如

```air
.
true
false
abc
1.23E-3
>=
```

## 定界形式

定界形式是由配对的定界符确定语法边界的语法形式。

- `'a'`
- `"a"`
- `(a)`
- `[a]`
- `{a}`

## 前缀定界形式

前缀定界形式是一种由前缀和定界符确定语法边界和语法规则的语法形式。

- `a'b'`
- `a"b"`
- `a(b)`
- `a[b]`
- `a{b}`

前缀定界形式是可拓展的无歧义语法形式。

## 语法形式

符号形式，定界形式，前缀定界形式统称为有界形式。

无界形式是由空白符分隔的有界形式序列。

所有的语法形式都是有界形式或者无界形式。

## 作用域

作用域是一种定界形式（`(a)`）或前缀定界形式（`a(b)`），作用域内外的语法解析彼此独立，作用域外部的语法解析不依赖作用域内部的语法特征。

作用域可以提供语法上下文。作用域继承外部作用域的上下文，并修改部分配置。

根作用域的上下文：右结合，正向调用。

### 空作用域

`(a)`

空作用域继承外部作用域的上下文，不修改任何配置。

空作用域用于增强可读性和辅助语法解析。

示例：

```air
(a)
(a b c)
(a b c) : d
a b (c : d)
```

### 结合方向作用域

`<(a)` 或 `>(a)`

作用域内左结合或右结合。

示例：

```air
<(a b c d e) === (a b c) d e
<(a) === a
<(a b) === a b
<(a b c) === a b c
<(a : b) === a : b
>(a b c d e) === a b (c d e)
>(a) === a
>(a b) === a b
>(a b c) === a b c
>(a : b) === a : b
```

### 调用作用域

`;(a)` 或 `!(a)`

作用域内正向调用或逆向调用。

示例：

```air
;(a b c) === ; b a : c
!(a b c) === ! b a : c
```

### 标签作用域

`;tag(a b ... c)` 或 `!tag(a b ... c)`

`a`，`b`，`...`，`c` 等为原子结构。`tag` 是不包含定界符的符号。

标签作用域递归正向或逆向调用标签 `tag`，输入为词汇列表。

任意非空作用域内将恢复原上下文配置。

标签作用域用于自定义语法。

标签作用域中的原子结构不组合成无界结构，故软关键字退化为其符号自身。

示例：

```air
;t(a) === (; t [a])
;t(;tag(a)) === (; t [(; tag [a])])
;t((a)) === (; t [(; t [a])])
;t(a b c d) === (; t [a, b, c, d])
;t(: ; ! ?) === (; t [:, ;, !, ?])
!t(a [b, c, d] e) === (! t [a, [(! t [b]), (! t [c]), (! t [d])], e])
!t(a b (c d e)) === (! t [a, b, (! t [c d e])])
!+(a b) === (! + [a, b])
```

## 字面量

### 原子字面量

原子字面量内部使用大写字母或非字母符号分段。

[原子字面量语法](./Air%20语言语法/原子字面量语法.md)

### 复合字面量

[复合字面量语法](./Air%20语言语法/复合字面量语法.md)

## 参考

[语法参考](./Air%20语言语法/语法参考.md)
