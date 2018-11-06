# tflite

### Download Models Using

```mathematica
src=Import["https://raw.githubusercontent.com/tensorflow/models/master/research/slim/nets/mobilenet_v1.md","Text"];
StringRiffle[
  Map[
    StringJoin["wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/",#,"tgz && tar -xvf ",#,"tgz"]&,
    Flatten[
        StringCases[StringSplit[src,"\n"],
        ___~~"http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/"~~r__~~"tgz)"~~___->r]
    ]
  ],
  "\n"
]
```

which generates

```
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_224.tgz && tar -xvf mobilenet_v1_1.0_224.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_192.tgz && tar -xvf mobilenet_v1_1.0_192.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_160.tgz && tar -xvf mobilenet_v1_1.0_160.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_128.tgz && tar -xvf mobilenet_v1_1.0_128.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_224.tgz && tar -xvf mobilenet_v1_0.75_224.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_192.tgz && tar -xvf mobilenet_v1_0.75_192.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_160.tgz && tar -xvf mobilenet_v1_0.75_160.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_128.tgz && tar -xvf mobilenet_v1_0.75_128.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_224.tgz && tar -xvf mobilenet_v1_0.5_224.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_192.tgz && tar -xvf mobilenet_v1_0.5_192.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_160.tgz && tar -xvf mobilenet_v1_0.5_160.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_128.tgz && tar -xvf mobilenet_v1_0.5_128.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_224.tgz && tar -xvf mobilenet_v1_0.25_224.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_192.tgz && tar -xvf mobilenet_v1_0.25_192.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_160.tgz && tar -xvf mobilenet_v1_0.25_160.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_128.tgz && tar -xvf mobilenet_v1_0.25_128.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_224_quant.tgz && tar -xvf mobilenet_v1_1.0_224_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_192_quant.tgz && tar -xvf mobilenet_v1_1.0_192_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_160_quant.tgz && tar -xvf mobilenet_v1_1.0_160_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_128_quant.tgz && tar -xvf mobilenet_v1_1.0_128_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_224_quant.tgz && tar -xvf mobilenet_v1_0.75_224_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_192_quant.tgz && tar -xvf mobilenet_v1_0.75_192_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_160_quant.tgz && tar -xvf mobilenet_v1_0.75_160_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_128_quant.tgz && tar -xvf mobilenet_v1_0.75_128_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_224_quant.tgz && tar -xvf mobilenet_v1_0.5_224_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_192_quant.tgz && tar -xvf mobilenet_v1_0.5_192_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_160_quant.tgz && tar -xvf mobilenet_v1_0.5_160_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_128_quant.tgz && tar -xvf mobilenet_v1_0.5_128_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_224_quant.tgz && tar -xvf mobilenet_v1_0.25_224_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_192_quant.tgz && tar -xvf mobilenet_v1_0.25_192_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_160_quant.tgz && tar -xvf mobilenet_v1_0.25_160_quant.tgz
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_128_quant.tgz && tar -xvf mobilenet_v1_0.25_128_quant.tgz
```
