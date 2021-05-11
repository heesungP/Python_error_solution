# Python_error_solution
파이썬 사용하다 생긴 오류에 대한 해결책 정리

# Keras

## - 2021.05.11 : AttributeError: module 'tensorflow.python.framework.ops' has no attribute '_TensorLike'

from keras.layers import SimpleRNN
from keras.layers import Dense, Input
from keras.models import Model

강의에서 위와 같이 keras layer와 model을 import 하라는 상황이었는데 Attribute Error가 발생

### sol
keras 앞에 tensorflow.을 붙여 해결

from tensorflow.keras.layers import SimpleRNN
from tensorflow.keras.layers import Dense, Input
from tensorflow.keras.models import Model
