# Extensibility
To create a new operational module if your modeling needed, give the following Python code:

```py
import math

@node
def sine(x):
    return math.sin(x)


@node(format="$1 ^ $2")
def power(x, y):
    return x ** y
```

By importing it in the *Manage Extensions* menu, you can use the defined nodes as if they were native, as in the image below.

![O editor de nós incluindo os nós customizados de seno e potência](../readme/demo-with-extensions-nodes.png)

The code can be used to simulate just like native nodes.

![Plotagem das EDOs utilizando nós customizados](../readme/demo-with-extensions-simulation.png)
