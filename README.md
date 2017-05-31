# keras-frcnn
This is a fork repository of https://github.com/yhenon/keras-frcnn

## Environment
- python 3.6
- tensorflow 1.1

## Notice!!!
### 1. Fix a bug of tensorflow

K.rnn method has not input_length argument. So, You must comment out it!!!!!

```
#tensorflow/contrib/keras/python/keras/layers/wrappers.py#188-189
def call(self, inputs, mask=None):
      .......
      _, outputs, _ = K.rnn(
          step,
          inputs,
          initial_states=[], #input_length=input_shape[1],
          unroll=False)
```


### 2. Not work at theano backend.

## Usage
### Learn
python train_frcnn.py -p < DataDir >

### Test
python test_frcnn.py -p < DataDir >
