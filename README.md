# HuBMAP-Hacking-the-Kidney
This was my submission to a Kaggle competition on identify glomeruli in human kidney tissue images.

## Challenges
One of the main challenges for this task was memory management! For one each WSI comes in a TIFF format with a size of 400 MB to 5 GB, compressed. Once you read each file they take up 6 - 11 GB of memory on the RAM. One solution is to take send entire images to the GPU on the fly for training. However given the size of the images, this approach severly bottlenecks the GPU during training because reading and decompressing will be slow. Also loading entire images onto the GPU leaves very little room for the classifier and the optimizer. To overcome these two issues, you need a different solution. The better practical solution is to create overlapping cuts of the images. This has the additional benefit of more randomization during training. 

Coming SoOn!
<p align="center">
<img width="800" alt="kidney" src="https://user-images.githubusercontent.com/65843134/151290141-5fc25515-8948-4f7f-9947-43f699df3fe7.png">
</p>
