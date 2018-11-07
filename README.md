# tflite

### Download TFlite Models Using

```mathematica
src = Import[
   "https://raw.githubusercontent.com/tensorflow/tensorflow/r1.12/\
tensorflow/contrib/lite/g3doc/models.md", "Text"];
getURLs[base_] := 
 StringRiffle[
  Map[StringJoin["wget " <> base, #, 
     "tgz && mkdir " <> StringTrim[#, "."] <> " && tar -xvf ", #, 
     "tgz -C `pwd`/", StringTrim[#, "."]] &, 
   Flatten[StringCases[
     StringSplit[src, "\n"], ___ ~~ base ~~ r__ ~~ "tgz)" ~~ ___ -> 
      r]]], "\n"]
StringRiffle[
 Flatten[{
   getURLs[
    "https://storage.cloud.google.com/download.tensorflow.org/models/\
tflite/"],
   getURLs[
    "https://storage.googleapis.com/download.tensorflow.org/models/\
tflite/model_zoo/upload_20180427/"],
   getURLs[
    "https://storage.googleapis.com/download.tensorflow.org/models/\
tflite_11_05_08/"],
   getURLs[
    "https://storage.googleapis.com/download.tensorflow.org/models/\
tflite/model_zoo/upload_20180427/"],
   getURLs[
    "http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/"],\

   getURLs["http://download.tensorflow.org/models/tflite_11_05_08/"],
   getURLs[
    "http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/"]
   }],
 "\n"
 ]
```

which generates

```
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_0.5_224_09_07_2018.tgz && mkdir mnasnet_0.5_224_09_07_2018 && tar -xvf mnasnet_0.5_224_09_07_2018.tgz -C `pwd`/mnasnet_0.5_224_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_0.75_224_09_07_2018.tgz && mkdir mnasnet_0.75_224_09_07_2018 && tar -xvf mnasnet_0.75_224_09_07_2018.tgz -C `pwd`/mnasnet_0.75_224_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_224_09_07_2018.tgz && mkdir mnasnet_1.0_224_09_07_2018 && tar -xvf mnasnet_1.0_224_09_07_2018.tgz -C `pwd`/mnasnet_1.0_224_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.3_224_09_07_2018.tgz && mkdir mnasnet_1.3_224_09_07_2018 && tar -xvf mnasnet_1.3_224_09_07_2018.tgz -C `pwd`/mnasnet_1.3_224_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_96_09_07_2018.tgz && mkdir mnasnet_1.0_96_09_07_2018 && tar -xvf mnasnet_1.0_96_09_07_2018.tgz -C `pwd`/mnasnet_1.0_96_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_128_09_07_2018.tgz && mkdir mnasnet_1.0_128_09_07_2018 && tar -xvf mnasnet_1.0_128_09_07_2018.tgz -C `pwd`/mnasnet_1.0_128_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_160_09_07_2018.tgz && mkdir mnasnet_1.0_160_09_07_2018 && tar -xvf mnasnet_1.0_160_09_07_2018.tgz -C `pwd`/mnasnet_1.0_160_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_192_09_07_2018.tgz && mkdir mnasnet_1.0_192_09_07_2018 && tar -xvf mnasnet_1.0_192_09_07_2018.tgz -C `pwd`/mnasnet_1.0_192_09_07_2018
wget https://storage.cloud.google.com/download.tensorflow.org/models/tflite/mnasnet_1.0_224_09_07_2018.tgz && mkdir mnasnet_1.0_224_09_07_2018 && tar -xvf mnasnet_1.0_224_09_07_2018.tgz -C `pwd`/mnasnet_1.0_224_09_07_2018
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/densenet_2018_04_27.tgz && mkdir densenet_2018_04_27 && tar -xvf densenet_2018_04_27.tgz -C `pwd`/densenet_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/squeezenet_2018_04_27.tgz && mkdir squeezenet_2018_04_27 && tar -xvf squeezenet_2018_04_27.tgz -C `pwd`/squeezenet_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/nasnet_mobile_2018_04_27.tgz && mkdir nasnet_mobile_2018_04_27 && tar -xvf nasnet_mobile_2018_04_27.tgz -C `pwd`/nasnet_mobile_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/nasnet_large_2018_04_27.tgz && mkdir nasnet_large_2018_04_27 && tar -xvf nasnet_large_2018_04_27.tgz -C `pwd`/nasnet_large_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_v3_2018_04_27.tgz && mkdir inception_v3_2018_04_27 && tar -xvf inception_v3_2018_04_27.tgz -C `pwd`/inception_v3_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_v4_2018_04_27.tgz && mkdir inception_v4_2018_04_27 && tar -xvf inception_v4_2018_04_27.tgz -C `pwd`/inception_v4_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_resnet_v2_2018_04_27.tgz && mkdir inception_resnet_v2_2018_04_27 && tar -xvf inception_resnet_v2_2018_04_27.tgz -C `pwd`/inception_resnet_v2_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite_11_05_08/resnet_v2_101.tgz && mkdir resnet_v2_101 && tar -xvf resnet_v2_101.tgz -C `pwd`/resnet_v2_101
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/densenet_2018_04_27.tgz && mkdir densenet_2018_04_27 && tar -xvf densenet_2018_04_27.tgz -C `pwd`/densenet_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/squeezenet_2018_04_27.tgz && mkdir squeezenet_2018_04_27 && tar -xvf squeezenet_2018_04_27.tgz -C `pwd`/squeezenet_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/nasnet_mobile_2018_04_27.tgz && mkdir nasnet_mobile_2018_04_27 && tar -xvf nasnet_mobile_2018_04_27.tgz -C `pwd`/nasnet_mobile_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/nasnet_large_2018_04_27.tgz && mkdir nasnet_large_2018_04_27 && tar -xvf nasnet_large_2018_04_27.tgz -C `pwd`/nasnet_large_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_v3_2018_04_27.tgz && mkdir inception_v3_2018_04_27 && tar -xvf inception_v3_2018_04_27.tgz -C `pwd`/inception_v3_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_v4_2018_04_27.tgz && mkdir inception_v4_2018_04_27 && tar -xvf inception_v4_2018_04_27.tgz -C `pwd`/inception_v4_2018_04_27
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/model_zoo/upload_20180427/inception_resnet_v2_2018_04_27.tgz && mkdir inception_resnet_v2_2018_04_27 && tar -xvf inception_resnet_v2_2018_04_27.tgz -C `pwd`/inception_resnet_v2_2018_04_27
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.25_128.tgz && mkdir mobilenet_v1_0.25_128 && tar -xvf mobilenet_v1_0.25_128.tgz -C `pwd`/mobilenet_v1_0.25_128
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.25_160.tgz && mkdir mobilenet_v1_0.25_160 && tar -xvf mobilenet_v1_0.25_160.tgz -C `pwd`/mobilenet_v1_0.25_160
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.25_192.tgz && mkdir mobilenet_v1_0.25_192 && tar -xvf mobilenet_v1_0.25_192.tgz -C `pwd`/mobilenet_v1_0.25_192
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.25_224.tgz && mkdir mobilenet_v1_0.25_224 && tar -xvf mobilenet_v1_0.25_224.tgz -C `pwd`/mobilenet_v1_0.25_224
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.5_128.tgz && mkdir mobilenet_v1_0.5_128 && tar -xvf mobilenet_v1_0.5_128.tgz -C `pwd`/mobilenet_v1_0.5_128
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.5_160.tgz && mkdir mobilenet_v1_0.5_160 && tar -xvf mobilenet_v1_0.5_160.tgz -C `pwd`/mobilenet_v1_0.5_160
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.5_192.tgz && mkdir mobilenet_v1_0.5_192 && tar -xvf mobilenet_v1_0.5_192.tgz -C `pwd`/mobilenet_v1_0.5_192
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.5_224.tgz && mkdir mobilenet_v1_0.5_224 && tar -xvf mobilenet_v1_0.5_224.tgz -C `pwd`/mobilenet_v1_0.5_224
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.75_128.tgz && mkdir mobilenet_v1_0.75_128 && tar -xvf mobilenet_v1_0.75_128.tgz -C `pwd`/mobilenet_v1_0.75_128
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.75_160.tgz && mkdir mobilenet_v1_0.75_160 && tar -xvf mobilenet_v1_0.75_160.tgz -C `pwd`/mobilenet_v1_0.75_160
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.75_192.tgz && mkdir mobilenet_v1_0.75_192 && tar -xvf mobilenet_v1_0.75_192.tgz -C `pwd`/mobilenet_v1_0.75_192
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_0.75_224.tgz && mkdir mobilenet_v1_0.75_224 && tar -xvf mobilenet_v1_0.75_224.tgz -C `pwd`/mobilenet_v1_0.75_224
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_1.0_128.tgz && mkdir mobilenet_v1_1.0_128 && tar -xvf mobilenet_v1_1.0_128.tgz -C `pwd`/mobilenet_v1_1.0_128
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_1.0_160.tgz && mkdir mobilenet_v1_1.0_160 && tar -xvf mobilenet_v1_1.0_160.tgz -C `pwd`/mobilenet_v1_1.0_160
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_1.0_192.tgz && mkdir mobilenet_v1_1.0_192 && tar -xvf mobilenet_v1_1.0_192.tgz -C `pwd`/mobilenet_v1_1.0_192
wget http://download.tensorflow.org/models/mobilenet_v1_2018_02_22/mobilenet_v1_1.0_224.tgz && mkdir mobilenet_v1_1.0_224 && tar -xvf mobilenet_v1_1.0_224.tgz -C `pwd`/mobilenet_v1_1.0_224
wget http://download.tensorflow.org/models/tflite_11_05_08/mobilenet_v2_1.0_224.tgz && mkdir mobilenet_v2_1.0_224 && tar -xvf mobilenet_v2_1.0_224.tgz -C `pwd`/mobilenet_v2_1.0_224
wget http://download.tensorflow.org/models/tflite_11_05_08/mobilenet_v2_1.0_224_quant.tgz && mkdir mobilenet_v2_1.0_224_quant && tar -xvf mobilenet_v2_1.0_224_quant.tgz -C `pwd`/mobilenet_v2_1.0_224_quant
wget http://download.tensorflow.org/models/tflite_11_05_08/inception_v3_quant.tgz && mkdir inception_v3_quant && tar -xvf inception_v3_quant.tgz -C `pwd`/inception_v3_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_128_quant.tgz && mkdir mobilenet_v1_0.25_128_quant && tar -xvf mobilenet_v1_0.25_128_quant.tgz -C `pwd`/mobilenet_v1_0.25_128_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_160_quant.tgz && mkdir mobilenet_v1_0.25_160_quant && tar -xvf mobilenet_v1_0.25_160_quant.tgz -C `pwd`/mobilenet_v1_0.25_160_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_192_quant.tgz && mkdir mobilenet_v1_0.25_192_quant && tar -xvf mobilenet_v1_0.25_192_quant.tgz -C `pwd`/mobilenet_v1_0.25_192_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.25_224_quant.tgz && mkdir mobilenet_v1_0.25_224_quant && tar -xvf mobilenet_v1_0.25_224_quant.tgz -C `pwd`/mobilenet_v1_0.25_224_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_128_quant.tgz && mkdir mobilenet_v1_0.5_128_quant && tar -xvf mobilenet_v1_0.5_128_quant.tgz -C `pwd`/mobilenet_v1_0.5_128_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_160_quant.tgz && mkdir mobilenet_v1_0.5_160_quant && tar -xvf mobilenet_v1_0.5_160_quant.tgz -C `pwd`/mobilenet_v1_0.5_160_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_192_quant.tgz && mkdir mobilenet_v1_0.5_192_quant && tar -xvf mobilenet_v1_0.5_192_quant.tgz -C `pwd`/mobilenet_v1_0.5_192_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.5_224_quant.tgz && mkdir mobilenet_v1_0.5_224_quant && tar -xvf mobilenet_v1_0.5_224_quant.tgz -C `pwd`/mobilenet_v1_0.5_224_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_128_quant.tgz && mkdir mobilenet_v1_0.75_128_quant && tar -xvf mobilenet_v1_0.75_128_quant.tgz -C `pwd`/mobilenet_v1_0.75_128_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_160_quant.tgz && mkdir mobilenet_v1_0.75_160_quant && tar -xvf mobilenet_v1_0.75_160_quant.tgz -C `pwd`/mobilenet_v1_0.75_160_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_192_quant.tgz && mkdir mobilenet_v1_0.75_192_quant && tar -xvf mobilenet_v1_0.75_192_quant.tgz -C `pwd`/mobilenet_v1_0.75_192_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_0.75_224_quant.tgz && mkdir mobilenet_v1_0.75_224_quant && tar -xvf mobilenet_v1_0.75_224_quant.tgz -C `pwd`/mobilenet_v1_0.75_224_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_128_quant.tgz && mkdir mobilenet_v1_1.0_128_quant && tar -xvf mobilenet_v1_1.0_128_quant.tgz -C `pwd`/mobilenet_v1_1.0_128_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_160_quant.tgz && mkdir mobilenet_v1_1.0_160_quant && tar -xvf mobilenet_v1_1.0_160_quant.tgz -C `pwd`/mobilenet_v1_1.0_160_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_192_quant.tgz && mkdir mobilenet_v1_1.0_192_quant && tar -xvf mobilenet_v1_1.0_192_quant.tgz -C `pwd`/mobilenet_v1_1.0_192_quant
wget http://download.tensorflow.org/models/mobilenet_v1_2018_08_02/mobilenet_v1_1.0_224_quant.tgz && mkdir mobilenet_v1_1.0_224_quant && tar -xvf mobilenet_v1_1.0_224_quant.tgz -C `pwd`/mobilenet_v1_1.0_224_quant
```

### Download MobileNet Using

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
