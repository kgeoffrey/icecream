
## IceCream

Icecream is a light-weight deep learning framework that I created to experiment with optimizers.

#### Example:

```Julia
using IceCream
using Plots

X_train, y_train, X_test, y_test = IceCream.TitanicDataSet()

model = icecream()

structure = layers(
    dense(4, fastsigmoid),
    dense(3, swish),
    dense(1, sigmoid))

compile(model,
    layers = structure,
    X_train = X_train,
    Y_train = y_train,
    loss = crossentropy,
    batchsize = 100)

train!(model, optimizer = NADAM, α = 0.001, epochs = 20)
plot(model.model_loss)
```
