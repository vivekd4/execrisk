# execrisk

**给输出的可执行性风险打分并按阈值给出通过与否。**

`execrisk` —— 为每一项打分并与阈值比较，明确标出通过、边界与不通过三档

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`execrisk.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install vivekd4-execrisk
```

装完直接用命令名调用：

```bash
execrisk --help
```

也可以不用安装，直接把 `execrisk.py` 拷走用——它只依赖标准库。

## 为什么需要它

阈值边界单独成档，不把「刚好压在阈值上」混进通过里

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 输出的可执行性风险 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python execrisk.py --file input.txt
python execrisk.py --text "示例内容"
python execrisk.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 阈值是固定值，不随数据自适应。
- 只判定达标与否，不解释分数来源。

## 跑测试

```bash
python test_execrisk.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/vivekd4/execrisk>

---

## 关于作者

vivekd4 做输出的可执行性风险相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://vivekd4.github.io>
- 仓库：<https://github.com/vivekd4/execrisk>

## 许可

MIT，见 [LICENSE](LICENSE)。
