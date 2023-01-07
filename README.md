# Fast Pose Human Estimation

<p align='justify'>
Nowadays, many models are based on two famous models, <a href="https://arxiv.org/abs/1603.06937">HourGlass</a> and <a href="https://arxiv.org/abs/1505.04597">U-Net</a> to estimate human pose. These two models consist of Encoder-Decoders stacks with skip connections between them. Based on the model, each skip connection is a Residual Block or an Identify connection. The structure of these two models is shown in the below pictures.
</p>
<br />
<p align="center">
<img src="https://github.com/HosseinPAI/Fast-Pose-Human-Estimation/blob/master/pics/HourGlass.png" alt="HourGlass Model"  width="700" height='300'/>
<br />
<sub>
HourGlass Model
</sub>
</p>
<br />
<p align="center">
<img src="https://github.com/HosseinPAI/Fast-Pose-Human-Estimation/blob/master/pics/U-NET.png" alt="U-Net Model"  width="500" height='350'/>
<br />
<sub>
U-Net Model
</sub>
</p>

<p align='justify'>
This project is an implementation of <a href="https://arxiv.org/abs/2002.11098">Toward fast and accurate human pose estimation via soft-gated skip connections</a> using Pytorch. The main structure of this model is related to previous models with adding new skip connections. The model and the structure of the skip connection are presented below.
</p>
<br />
<p align="center">
<img src="https://github.com/HosseinPAI/Fast-Pose-Human-Estimation/blob/master/pics/model_architecture.png" alt="Fast Human Pose Model"  width="700" height='300'/>
<br />
<sub>
Human Pose Estimation via Soft-Gated Skip Connections Model
</sub>
</p>
<br />
<p align="center">
<img src="https://github.com/HosseinPAI/Fast-Pose-Human-Estimation/blob/master/pics/skip.png" alt="Skip Connection"  width="400" height='250'/>
<br />
<sub> 
Soft-Gated Skip Connections Structure
</sub>
</p>

<br />
<p align="justify">
The original paper first pre-trains the model by <a href="http://human-pose.mpi-inf.mpg.de/">MPII dataset</a>. Then it utilizes <a href="https://sam.johnson.io/research/lsp.html">LSP dataset</a> to improve the model performance. Here we just use LSP dataset. However, we augmented training data with various transformations, then all the images should resize to the same dimensions before feeding into the model.
To train the model, please download the dataset and extract it to a specific location, finally passing both the images folder and joints.mat file as arguments to the 'main.py' file. As an example, consider the following command:
</p>

```
python main.py --images_path ./lsp_dataset/images/ --joints_path ./lsp_dataset/joints.mat
```
You would set other training options by passing more arguments. To check other options, use the command below:
```
python main.py --help
```
