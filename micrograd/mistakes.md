So when calling loss.backward(), it shows the grads of the nodes.

Yet when running through the parameters and printing their grads, most of them are 0.


Was calling m.parameters instead of n.parameters



# Recursively passing x through each layer

In this code block inside the MLP function:

```python
for layer in self.layers:
    x = layer(x)

return x
```

I originally set it to `out = layer(x)`, then `return out`.

However, the problem with this is that it wouldn't do the clever recursive reassignment essential to this function.

By declaring `x = layer(x)` in a for loop, each layer will initialize with x, then set that to be x. Then the next layer
will initialize using THAT x. So it recursively goes down the line iterating over and over again so it passes the x inputs
correctly.

^ that is for the xs. For initializing the layers with the correct nin and nouts, we use the net[i], net[i+1] technique.
