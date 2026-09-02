# START

- import numpy

# VALUE CLASS


## __init__
- self.blank = blank
- What data does a value need to hold in order to backpropagate correctly?

## __repr__(self)
-return f"Value(data={self.data})"

## The other expressions
- other = other if isinstance(other, Value) else Value(other) # makes operations like a + 1 work because it converts 1 to a value object with a data attribute

What do the expressions need to hold? Remember the closure

- Remember each expression has different derivatives

__pow__
assert isinstance(other, (int, float)), "only supporting int/float powers for now"

def __radd__(self, other):
        return self + other

__truediv__ for division

__neg__(self) for negative

def backward(self):
    topo graph
    call reversed on nodes


# BUILDING THE NET

nin, nout, nouts
self.w = [Value(random.uniform(-1, 1)) for _ in range(nin)]

__call__ fires the neuron

## NEURON
(self, nin)
__call__(self, x) where x is an input list

Multiply the weights and values of the inputs together then sum them up and add teh bias on top. Use broadcasting

out = act.tanh()



## LAYER
nin, nout

def __init__(self, nin, nout): # nout is used to define the number of neurons in the layer; number of outputs (because each neuron has 1 output)

initialize an array of neurons given the desired amount(nout) for _ in range

 calls n(x) for each neuron given the x array (its __call__ function), computing the final output for each neuron, then stores the outputs in a list



## MLP
def __init__(self, nin, nouts): # nouts is a list of nout(s): defines the sizes of all the layers in our net. Here, nin only represents the number of inputs to the network.


adds the number of inputs to the network to the beginning of nouts, essentially creating a list with all inputs in the network
sz = 

creates a list of Layer objects with each one having an input equal to the previous layer's output 
self.layers = 

def __call__(self, x)

initializes each layer with x as the input



nin, nouts
