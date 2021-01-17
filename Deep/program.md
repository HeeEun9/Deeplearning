### Tensorflow 
- Tensor : 다차원 배열 (Multi-dimensional Array)
- 특징을 추출해주는 [Convoulution layer](https://tykimos.github.io/2017/01/27/CNN_Layer_Talk/)
1. [Keras Sequential](http://blog.daum.net/sualchi/13720852)
    + Keras의 Sequential 모델은 레이어들의 선형 스택(a linear stack of layers)로 되어있음
    ```python
    # model에 생성
    from keras.models import Sequential
    from keras.layers import Dense, Activation
    model = Sequential([
    Dense(32, input_shape=(784,)), # 클래스32
    Activation('relu'),             # 선형 함수
    Dense(10),                       # 클래스 10
    Activation('softmax'),])
    
    # add() 활용 계층 추가
    model = Sequential()
    model.add(Dense(32, input_dim=784))
    model.add(Activation('relu'))
    model.add(Dense(10, input_dim=32)) #
    model.add(Activation('softmax'))    #
    ```
2. [tf.keras.models.Sequential.compile](https://www.tensorflow.org/api_docs/python/tf/keras/Model)
```python
compile(
    optimizer='rmsprop', loss=None, metrics=None, loss_weights=None,
    weighted_metrics=None, run_eagerly=None, steps_per_execution=None, **kwargs
)
```
    - optimizer :최적화모델 Adadelta, Adagrad, Adam, Adamax, Ftrl, Nadam, Optimizer, RMSprop, SGD
    - loss : 
    - metrics :
    - loss_weights : 
    - weighted_metrics : 
    - run_eagerly :
    - steps_per_execution
    - **kwargs : 


###### [model생성](https://ebbnflow.tistory.com/128?category=738689)
- Sequential API : 단순한 층 쌓기 가능, 직관적 
- Functional API : 복잡한 층 쌓기 가능
##### [Tensor 기본](https://codetorial.net/tensorflow/basics_of_tensor.html)
```python
a = tf.constant(1) # constant는 상수 텐서를 만듬
b = tf.constant([2,3])
print(a) # tf.Tensor(1, shape=(), dtype=int32)
print(b) # tf.Tensor([2,3], shape=(2,),dtype=int32)

c = tf.zeros([2, 3]) #zero는 0으로 채워진 tensor 만듬 / ones는 1로 채워진 tensor 만듬
print(c)
tf.Tensor([[0. 0. 0.][0. 0. 0.]], shape=(2, 3), dtype=float32)
print(a.dtype, a.shape) # <dtype: 'int32'> 자료형 반환
```
##### [🍇initializers](https://www.tensorflow.org/api_docs/python/tf/keras/initializers/HeNormal)
##### [🥑Dense](https://www.tensorflow.org/api_docs/python/tf/keras/layers/Dense?hl=ko)
- model.add(Dense(50, kernel_initializer='he_normal')) : he_normal :: It draws samples from a truncated normal distribution centered on 0 with stddev = sqrt(2 / fan_in) where fan_in is the number of input units in the weight tensor.

- model.add(Activation('sigmoid'))
-----------------------------------