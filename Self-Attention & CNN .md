## Original link

ON THE RELATIONSHIP BETWEEN SELF-ATTENTION AND CONVOLUTIONAL LAYERS

原文连接：https://arxiv.org/abs/1911.03584

### My inspiration from Lhy professor's vedio

在处理图像问题上：
self-attention把一张图像中的每个像素点看做一个向量，向量长度为通道数3。
像素之间计算相关系数：每个像素向量生成对应的**q**,**k**,**v**三个向量，该像素的**q**和其他像素的**k**点积得到相关系数，并根据**相关系数**和每个像素的**v**生成对应于该像素向量的一个新向量，该向量蕴含有其他像素点的相关信息。对新向量中的3个值进行全连接输出。

CNN在图像中选取一个receptive field范围进行局部处理，选择3*3*3的filter则会对该区域的27个值进行全连接输出，也就是filter中的27个系数与图像中实际输入的27个数值依次相乘。

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/jokerlj92/220320_ML/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.
