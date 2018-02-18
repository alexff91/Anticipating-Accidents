# Anticipating Accidents in Dashcam Videos
By Fu-Hsiang Chan, Yu-Ting Chen, Yu Xiang, Min Sun.

### Introduction

Anticipating Accidents in Dashcam Videos is initially described in a [ACCV 2016 paper](https://drive.google.com/file/d/0ByuDEGFYmWsbNkVxcUxhdDRVRkU/view).
We propose a Dynamic-Spatial-Attention (DSA) Recurrent Neural Network (RNN) for anticipating accidents in dashcam videos.

### Requirements

##### Tensoflow 0.12.1
##### Opencv 2.4.9
##### Matplotlib
##### Numpy

### Model Flowchart
![Alt text](./img/flowchart.png "Optional title")


### Dataset & Features

* Dataset : [link](http://aliensunmin.github.io/project/dashcam/) (Download the file and put it in "datatset/videos" folder.)

* CNN features : [link](https://drive.google.com/file/d/0B8xi2Pbo0n2gRGpzWUEzRTU2WUk/view?usp=sharing) (Download the file and put it in "dataset/features" folder.)

* Annotation : [link](https://drive.google.com/file/d/0B8xi2Pbo0n2gdTlwT2NXdS1NTFE/view?usp=sharing)

If you need the ground truth of object bounding box and accident location, you can download it.

The format of annotation:

<image name, track_ID, class , x1, y1, x2, y2, 0/1 (no accident/ has accident)>

### Usage

#### Run Demo
```
python accident.py --model ./demo_model/demo_model
```

#### Training
```
python accident.py --mode train --gpu gpu_id
```

#### Testing
```
python accident.py --mode test --model model_path --gpu gpu_id
```

### Citing

Please cite this paper in your publications if you use this code for your research:

    @inproceedings{chan2016anticipating,
        title={Anticipating accidents in dashcam videos},
        author={Chan, Fu-Hsiang and Chen, Yu-Ting and Xiang, Yu and Sun, Min},
        booktitle={Asian Conference on Computer Vision},
        pages={136--153},
        year={2016},
        organization={Springer}
    }

### LSTM
Долгая краткосрочная память (англ. Long short-term memory; LSTM) — разновидность архитектуры рекуррентных нейронных сетей, предложенная в 1997 году Сеппом Хохрайтером и Юргеном Шмидхубером[2]. Как и большинство рекуррентных нейронных сетей, LSTM-сеть является универсальной в том смысле, что при достаточном числе элементов сети она может выполнить любое вычисление, на которое способен обычный компьютер, для чего необходима соответствующая матрица весов, которая может рассматриваться как программа. В отличие от традиционных рекуррентных нейронных сетей, LSTM-сеть хорошо приспособлена к обучению на задачах классификации, обработки и прогнозирования временных рядов в случаях, когда важные события разделены временными лагами с неопределённой продолжительностью и границами. Относительная невосприимчивость к длительности временных разрывов даёт LSTM преимущество по отношению к альтернативным рекуррентным нейронным сетям, скрытым марковским моделям и другим методам обучения для последовательностей в различных сферах применения. Из множества достижений LSTM-сетей можно выделить наилучшие результаты в распознавании несегментированного слитного рукописного текста[3], и победу в 2009 году на соревнованиях по распознаванию рукописного текста (ICDAR[en]). LSTM-сети также используются в задачах распознавания речи, например LSTM-сеть была основным компонентом сети, которая в 2013 году достигла рекордного порога ошибки в 17,7 % в задаче распознавания фонем на классическом корпусе естественной речи TIMIT[en][4]. По состоянию на 2016 год ведущие технологические компании, включая Google, Apple, Microsoft и Baidu, используют LSTM-сети в качестве фундаментального компонента новых продуктов[5][6]/