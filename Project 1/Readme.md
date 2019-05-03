### Assignment 1A
https://colab.research.google.com/github/SETIADEEPANSHU/ExtensiveVisionAIProgramme/blob/master/Project%201/EVA_S1.ipynb

### Assignment 1B

Q1. What are Channels and Kernels (according to EVA)?

**Channels**
Channels are expected to contain similar types of features. An image can be divided into any number of channels i.e, combining various channels should give back the image. For example: Channel of all vertical lines, all red color, Arcs - combination of edges. Output of the kernel convolution gives the channel output.

**Filters/Kernels**
Kernels are known as filters in the context of convolutional neural networks. They are essentially small matrices which slide over the input image and deduce features from the input image by performing dot product between the values of the matrix in the receptive field and its own weights. As a result, values of weights in the kernels decide what type of features are learnt. The resultant sum of the dot product is called an activation map. An activation map forms one cell of the output volume of the convolution, and is generally referred to as an activation matrix. The rest of the activation matrix is then filled by sliding the kernel at a "stride" interval across the rest of the volume of the input channel. 

Q2. Why should we only (well mostly) use 3x3 Kernels?

Following are the reasons for using 3x3 kernels:
1) Using odd sized filter captures assymetricity of an object present in the image. For example: A triangle can be captured properly in an odd kernel. 
2) And the greater the size of the odd kernel it will increase the number of parameters, for example: 3x3 kernel unit will have 9*5=45 multiplication operations and 11x11 unit will have 121 operations when convoluted with an image of size 11x11
3) Since these kernels became common with VGG network and other SOT networks, Nvidia optimized this kernel a lot.

Q3. How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199?

199X199->197X197->195X195->193X193->191X191->189x189->187X187->185X185->183X183->181X181->179X179->177X177->175X175->173X173->171X171->169X169->167X167->165X165->163X163->161X161->159X159->157X157->155X155->153X153->151X151->149X149 147X147->145X145->143X143->141X141->139X139->137X137->135X135->133X133->131X131->129X129->127X127->125X125->123X123 121X121->119X119->117X117->115X115->113X113->111X111->109X109->107X107->105X105->103X103->101X101->99X99->97X97->95X95 93X93->91X91->89X89->87X87->85X85->83X83->81X81->79X79->77X77->75X75->73X73->71X71->69X69->67X67->65X65->63X63->61X61 59X59->57X57->55X55->53X53->51X51->49X49->47X47->45X45->43X43->41X41->39X39->37X37->35X35->33X33->31X31->29X29->27X27 25X25->23X23->21X21->19X19->17X17->15X15->13X13->11X11->9X9->7X7->5X5->3X3->1X1

The number of times convolution operation required to achieve full receptive field of the object in the image is 100
