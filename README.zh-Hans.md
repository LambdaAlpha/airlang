# Air 编程语言

Air 编程语言是一门实验性编程语言。它的主要目标是通用性和最优性。详见 [Air 语言设计目标](zh-Hans/Air%20语言设计目标.md)。

## Demo

```air
_"A demo of implementing a C-like for function"

do ; [
    c_for = function ; {
        context_access : mutable,
        call_mode : id,
        call : ctx : args -> do ; [
            [.init, .condition, .next, .body] = .args,
            .ctx | do ; [
                .init,
                .condition loop [
                    .body,
                    .next,
                ],
            ],
        ],
    },
    c_for [[i = 1, sum = 0], i <= 10, i = i + 1, sum = sum + i],
    sum
]
```

## 许可证

您可以选择使用

* Apache 2.0 许可证
  ([LICENSE-APACHE](LICENSE-APACHE) 或 <http://www.apache.org/licenses/LICENSE-2.0>)
* MIT 许可证
  ([LICENSE-MIT](LICENSE-MIT) 或 <http://opensource.org/licenses/MIT>)

## 贡献

除非您明确说明，否则您有意提交以纳入作品的任何贡献（如 Apache-2.0 许可证中所定义），均应按照上述方式获得双重许可，无任何附加条款或条件。
