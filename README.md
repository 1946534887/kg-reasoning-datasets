# Knowledge Graph Datasets

本目录整理了用于知识图谱表示学习、链接预测与推理实验的数据集。

## 目录结构

```text
data/
├── family/
├── fb15k-237/
├── umls/
└── WN18RR/
```

每个数据集目录包含以下文件：

| 文件 | 内容 |
| --- | --- |
| `train.txt` | 训练集三元组 |
| `valid.txt` | 验证集三元组 |
| `test.txt` | 测试集三元组 |
| `entities.txt` | 实体列表 |
| `relations.txt` | 关系列表 |
| `facts.txt` | 数据集事实集合 |

三元组文件每行一条记录，字段顺序为：

```text
head_entity<TAB>relation<TAB>tail_entity
```

部分文件使用制表符分隔，文本编码及数据集内部标识符应以原始数据文件为准。

## 数据集说明

- `FB15k-237`：Freebase 派生的知识图谱基准数据集。
- `WN18RR`：WordNet 派生的知识图谱基准数据集。
- `UMLS`：统一医学语言系统相关的知识图谱数据集。
- `family`：家庭关系知识图谱数据集；请在此补充原始来源或构建说明。

## 使用提示

读取三元组示例（Python）：

```python
from pathlib import Path

path = Path("fb15k-237/train.txt")
with path.open("r", encoding="utf-8") as f:
    for line in f:
        head, relation, tail = line.rstrip("\n").split("\t")
        # 在此处执行数据预处理或模型训练
```

发布或用于研究前，请核对各数据集的原始来源、引用要求和许可条款。尤其是 `family` 数据集，目前目录中未包含来源或许可说明。请勿在未确认授权的情况下公开分发数据。

## Citation and License

请根据各数据集原始发布页面补充引用信息和许可条款。本仓库当前未声明这些数据的再分发许可。
