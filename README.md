# ctxgrowth

**追踪智能体上下文长度的增长来源。**

`ctxgrowth` —— 按来源分段统计上下文的增长贡献，标出膨胀最快的部分

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`ctxgrowth.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install dawsonoffi-ctxgrowth
```

装完直接用命令名调用：

```bash
ctxgrowth --help
```

也可以不用安装，直接把 `ctxgrowth.py` 拷走用——它只依赖标准库。

## 为什么需要它

把「上下文长」拆成「哪一部分在长」，才知道该丢什么

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 智能体上下文膨胀 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python ctxgrowth.py --file input.txt
python ctxgrowth.py --text "示例内容"
python ctxgrowth.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 长度按字符与词统计，与具体 tokenizer 有偏差。
- 不判断长度是否「合理」，只报告分布。

## 跑测试

```bash
python test_ctxgrowth.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/dawsonoffi/ctxgrowth>

---

## 关于作者

dawsonoffi 做智能体上下文膨胀相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://dawsonoffi.github.io>
- 仓库：<https://github.com/dawsonoffi/ctxgrowth>

## 许可

MIT，见 [LICENSE](LICENSE)。
