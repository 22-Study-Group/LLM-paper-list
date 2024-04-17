# 多模态大模型MLLM相关论文

## BLIP2
[BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models](http://arxiv.org/abs/2301.12597)
- 使用Qformer对齐text和image的space  
- 脱离LLM，相似度等方法对QFormer进行训练

## MiniGPT系列
[MiniGPT-4: Enhancing Vision-Language Understanding with Advanced Large Language Models](http://arxiv.org/abs/2304.10592)
- 单单训练projection layer就达到了很好的效果
- 在二阶段数据集流水线中使用GPT辅助，解决一阶段的模型虽然能够理解图片但是输出的语句不通顺的问题。

[MiniGPT-v2: large language model as a unified interface for vision-language multi-task learning](http://arxiv.org/abs/2310.09478)
- 用类似p tuning的方式，在序列前增加了一个task token来适应不同的任务，这些就类似于LLM的special token，特殊token还有诸如开始结束标记[CLS] 或 </s>，分隔符[SEP] 或 |||，填充符[PAD] 或 <pad>，掩码[MASK]等等。是和普通的token一样的方法去训练的。
- 抛弃了BLIP2的结构，直接用一个Linear把图片映射到文本模态输入模型。并且因为高分辨率的图片会消耗很多token，所以4个image token合成一个，先用view把每4个堆叠到一个维度里面去，再用Linear实现4合1这里看代码就很清晰
- 训练视觉对齐到文本分三个阶段训练

## ALBEF
[Align before Fuse: Vision and Language Representation Learning with Momentum Distillation](http://arxiv.org/abs/2107.07651)
- 图文对比学习：准备5个假个真，然后分别和图片的embedding计算相似度，然后softmax得到logits和groundtruth计算交叉熵损失
- 其实后面看BGE的训练也有类似的部分，并且BGE的训练需要比较大的batchsize效果才好，说是这样比较能找到hard negative