# 高效训练/微调方法
## OpenAI的Instruction Tuning
[Finetuned Language Models are Zero-Shot Learners](https://openreview.net/forum?id=gEZrGCozdqR)
- 这篇提出一种Instruction Tuning的方法，通过模板制作11个类的问题，包含阅读理解、翻译等等训练模型，发现在新的未经训练的1类任务的表现也有提升。说明了Instruction Tuning的方法有助于提升模型理解能力。
- 不过这个方法在8B以下的模型反而有反效果，作者的意思是学习instruction tuning中的内容已经占据了模型的整个容量，使其在面对新任务时表现不佳。