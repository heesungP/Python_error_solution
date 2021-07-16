# Python_error_solution
파이썬 사용하다 생긴 오류에 대한 해결책 정리


# Tensorflow
## [2021.04.17]
### - tensorflow 1.x 버전으로 구현되어있는 코드를 2.x에서 사용하는 방법

```
import tensorflow as tf
tf.Variable...
tf.placeholder...
sess = tf.Session...
sess.run...
```

와 같은 코드가 구현되어있음
2.x 버전의 tf에서는 실행 불가능


### - Solution
```
import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()
```





# Keras
## [2021.05.11]
### - AttributeError: module 'tensorflow.python.framework.ops' has no attribute '_TensorLike'

```
from keras.layers import SimpleRNN
from keras.layers import Dense, Input
from keras.models import Model
```

강의에서 위와 같이 keras layer와 model을 import 하라는 상황이었는데 Attribute Error가 발생

### - Solution
keras 앞에 tensorflow.을 붙여 해결

```
from **tensorflow.**keras.layers import SimpleRNN
from **tensorflow.**keras.layers import Dense, Input
from **tensorflow.**keras.models import Model
```


# 기타
## [2021.05.17]
### - MemoryError: Unable to allocate 000 GiB for an array with shape (0000,0000) and data type float64

![python-oom](https://user-images.githubusercontent.com/67678405/118435357-cd380c80-b719-11eb-91e8-0ddba514f9f0.png)

### - Solution

- 구글링 결과 여러가지 솔루션이 있었지만, 가장 확실한거는 컴퓨터 메모리가 충분한 상태에서 진행하는 것인듯
- last-fm 데이터에 대한 matrix를 np로 만드는 과정에서 8.45GiB, (48123,23566) memory error가 떴었음
- 현재 연구실 컴퓨터의 메모리 중 **20.5GB** 사용하는 중이고 잘 돌아가고 있음



# Module Import
##[2021.06.30]
### - ModuleNotFoundError: No module named 'cv2'
```
import cv2
```
### - Solution
```
[Anaconda Prompt]
pip install opencv-python
```

##[2021.07.16]
### - ModuleNotFoundError: No module named 'kornia'
```
import kornia
```
### - Solution
```
[Anaconda Prompt]
pip install kornia
```
