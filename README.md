# ngspice-python

Code example to run Ngspice Raw File using Python Script

1. In this CMOS inverter example has been used.

>Go to directory where "simrun.raw" file is present.
>In the example, it is in Downloads folder
```sh
cd C:\Users\Hp\Downloads
```

2. Import NgSpicedata module using sys.path.append method
```sh
import sys
sys.path.append(r"C:\Users\Hp\Downloads")
from ngspicedata import *
```

3. Import Matplotlib module for plotting purpose
```sh
from pylab import *
import matplotlib.pyplot as pl
```

4. Load the simrun file using
```sh
data=NgspiceData("simrun.raw")
```

5. Print the simulation signal
```sh
sig_names = data.lssig('print') 
```

6. Store values in x an y
>In example code for inverter two signals "in" and "out" voltage is there.
```sh
x = data.evalsig('in')
y= data.evalsig('out')
```

7. Plot the Inverter Graph
```sh
fig = figure(1)
fig.clf()
plot(x,y,'b-')
grid(True)
pl.show()
```
![Output](graph.png)
   
