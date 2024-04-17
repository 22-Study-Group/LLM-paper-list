#  前置知识/经典论文
## ROPE编码
[RoFormer: Enhanced Transformer with Rotary Position Embedding](http://arxiv.org/abs/2104.09864)
- 目前大部分LLM（如llama，qwen）都在用的位置编码方式，优于trainable的位置编码（如gpt2，bert）
- 给不同位置的词向量在空间上做旋转，角度由序列长度决定