<h3 style="text-align:center">《Skilful precipitation nowcasting using deep generative models of radar》论文复现</h3>

***

<h4>论文摘要</h4>

论文提出了一个深度生成模型，用于雷达降水的概率即时预报，来解决现有方法中存在的难以捕捉重要的非线性事件，例如对流起始，以及在较长的提前时间内产生的即时预报比较模糊，只能准确预测低强度降雨等问题，该模型可以对最大1536公里 $\times$ 1280公里的区域生成逼真、时空一致的预测，预报时间提前5-90分钟。经定量验证，该模型即时预报的效果较现有方法更好，无需模糊处理。论文表明生成式即时预报可以提供概率预测，从而提高预报价值并支持操作效用，并且在分辨率和提前期比现有方法更胜一筹。

<br>

<h4>数据集</h4>

<h5>UK dataset</h5>

使用来自英国气象局 *RadarNet4* 网络的一系列雷达合成图像

[数据集访问](gs://dm-nowcasting/datasets/nowcasting_open_source_osgb/nimrod_osgb_1000m_yearly_splits/radar/20200718)

<br>

<h4>模型架构</h4>

这个即时预测模型是一个使用两个 *Discriminators* 和一个附加 *Regularization* 进行训练的 *Generator*

<h5>Generator架构</h5>

[![pkd7NKP.png](https://s21.ax1x.com/2024/06/14/pkd7NKP.png)](https://imgse.com/i/pkd7NKP)

<h5>Temporal Discriminator架构</h5>

[![pkd7ab8.png](https://s21.ax1x.com/2024/06/14/pkd7ab8.png)](https://imgse.com/i/pkd7ab8)

<h5>Spatial Discriminator架构</h5>

[![pkd70Ug.png](https://s21.ax1x.com/2024/06/14/pkd70Ug.png)](https://imgse.com/i/pkd70Ug)

<br>

<h4>依赖库</h4>

* dask == 2022.9.1
* matplotlib == 3.5.1
* numba == 0.55.1
* numpy == 1.21.0
* pandas == 1.4.1
* properscoring == 0.1
* pytorch-lightning == 1.5.10
* torchvision == 0.11.3
* pytorch

<br>

<h4>工作流程</h4>

[![pkd7B5Q.png](https://s21.ax1x.com/2024/06/14/pkd7B5Q.png)](https://imgse.com/i/pkd7B5Q)

<br>

<h4>实验结果</h4>

对于模型DGMR, PySTEPS, UNet, Axial attention，在 $T + 30, T+60$ 和 $T + 90$ 的未来时间的预测对比

[![pkd7rCj.png](https://s21.ax1x.com/2024/06/14/pkd7rCj.png)](https://imgse.com/i/pkd7rCj)
