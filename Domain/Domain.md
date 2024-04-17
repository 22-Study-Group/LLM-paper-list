# 垂直领域大模型相关论文
## 从预先训练阶段开始的中医大模型Qibo
[Qibo: A Large Language Model for Traditional Chinese Medicine](http://arxiv.org/abs/2403.16056)
- 阅读到一篇中医领域的大模型，感觉挺有参考价值，不同于大部分的领域模型，他是直接基于llama，没修改模型结构，但是在预训练语料文献上做的很全面。
- 采用[Instruction Tuning](zhuanlan.zhihu.com/p/408166011)，这里提一嘴，在instruction tuning的论文中，8B以下的模型使用会有反效果
- SFT阶段用了四类资料，首先是和我们一样设计了单轮和多轮对话，以及普通的文本来防止模型灾难性遗忘。其次增加了Instruction Data（实体识别，症状识别，阅读理解）并且自己弄了一套benchmark，用来和市面上的LLM做对比。