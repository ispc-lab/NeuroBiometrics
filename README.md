# NeuroBiometric: Eye Blink Based Biometric Authentication System Using Event-based Neuromorphic Vision Sensor
This repository contains the dataset in our paper `NeuroBiometric: Eye Blink Based Biometric Authentication System Using Event-based Neuromorphic Vision Sensor`. If you benefit from this repository, please cite our paper.
```
@ARTICLE{,
        title = {NeuroBiometric: Eye Blink Based Biometric Authentication System Using Event-based Neuromorphic Vision Sensor},
      journal = {IEEE/CAA Journal of Automatica Sinica},
         year = {2020},
        pages = {},
      author  = {Guang, Chen and Fa, Wang and Xiaoding, Yuan and Zhijun, Li and Zichen, Liang and Alois, Knoll}, 
       eprint = {} 
}
```
## Abstract
The rise of the Internet and identity authentication systems has brought convenience to people’s lives but has also brought potential risk of privacy leaks. Existing biometric authentication systems based on explicit and static features bear the risk of being attacked by mimicked data. This work proposes a highly efficient biometric authentication system based on transient eye blink signals that are precisely captured by a neuromorphic vision sensor with microsecond-level temporal resolution. The neuromorphic vision sensor only transmits the local pixel-level changes induced by the eye blinks where they occur, which leads to advantageous characteristics such as ultra-low latency response. We first propose a set of effective biometric features describing the motion, speed, energy and frequency signal of eye blinks based on microsecond temporal resolution of event densities. We then train the ensemble model and non-ensemble model with our NeuroBiometric dataset for biometrics authentication. The experiments show that our system is able to identify and verify the subjects with the ensemble model at an accuracy of 0.948 and with the nonensemble model at an accuracy of 0.925. The steadily low FPRs (about 0.002) and the highly dynamic features are not only hard to fake but also avoid recording visible characteristics of a user’s appearance. The proposed system sheds light on a new path towards safer authentication using neuromorphic vision sensors.
## Demo
Examples of our recorded dataset:
![Fig](https://github.com/tjtum-chenlab/NeuroBiometrics/blob/master/figs/data_series.png)

## Dataset
### Dataset Introduction
This repository has released the original dataset of NeuroBiometric.To study the biometric authentication system with an event-based neuromorphic vision sensor, we collected a new dataset with eye blink signals recorded by the DAVIS sensor named NeuroBiometric dataset.   
The DAVIS sensor we used is DAVIS346, which has a resolution of 346*260 pixels, a temporal resolution of 1 μs and an outstanding dynamic range (up to 140 dB). We have 45 volunteers (of whom, 23 are men and 22 are women) to participate in our recording.  

The dataset could be downloaded by https://share.weiyun.com/LoMK32g7.

### Dataset Collection
The dataset and codes will be available after our paper is accepted.
All the volunteers are in a normal psychological and physiological state.   
Only the facial region includes eyebrow and ocular is recorded by the DAVIS sensor. Additional 60 seconds of break time after every 120 seconds recording is to avoid unusual eye blink due to potential fatigue and distraction.  

The dataset was collected by Jaer-1.7.3, a Java tool for Address-Event Representation (AER) neuromorphic processing. Visit https://sourceforge.net/p/jaer/wiki/Home/ for more information and download.

### Dataset Naming
All the raw data are named in a format of 'Davis346redColor-yyyy-mm-ddTsxx-kk.aedat', in which 'yyyy-mm-dd' is the date when a piece of data was collected, 'xx' is the participant id, and 'kk' represents the video id of a participant. For an instance, 'Davis346redColor-2019-03-11Ts01-01.aedat' is the 1st vedio of participant 1, which recorded at '2019 Mar. 11th'.

## How to Use
### aedat_convert_csv.py
It helps to convert original 'aedat' data into serialized events.  
Outputs are csv files with serialized events in rows, each event is represented by a 4-dimension tuple: 'timestamp', 'x', 'y', 'pol'.
```
timestamp: timestamp when event is triggered.  
x, y: 2D location of event in a 346*260 canvas.  
pol: polarity of event, '1' for ON and '0' for OFF.  
```

### eyeblink_to_img.py
It helps to convert original 'aedat' data into images.  
A filteration process(introduced in our paper) is contained, but you can choose not to filter the raw data by set 'filter_flag' as False.
In addition, you can set 'binary' as True if binary images are expected as outputs.
```
binary = False         # True: output binary images
filter_flag = False    # True: use filter
```


## Contact 
Please contact Guang Chen (email:tj_autodrive@hotmail.com) for your questions about this repository.

