# sampleplan

**为不同任务推荐合适的采样参数。**

`sampleplan` —— 按任务类型给出温度、top-p 与最大长度的建议并说明依据

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`sampleplan.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install spmerton-sampleplan
```

装完直接用命令名调用：

```bash
sampleplan --help
```

也可以不用安装，直接把 `sampleplan.py` 拷走用——它只依赖标准库。

## 为什么需要它

每个建议都写清适用条件，不是一套固定参数

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 采样参数规划 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python sampleplan.py --file input.txt
python sampleplan.py --text "示例内容"
python sampleplan.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 阈值是固定值，不随数据自适应。
- 只判定达标与否，不解释分数来源。

## 跑测试

```bash
python test_sampleplan.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/spmerton/sampleplan>

---

## 关于作者

spmerton 做采样参数规划相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://spmerton.github.io>
- 仓库：<https://github.com/spmerton/sampleplan>

## 许可

MIT，见 [LICENSE](LICENSE)。
