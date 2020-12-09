
## Visualizing data

### matplotlib heatmap

![matplotlib heatmap](img/inflammation-01-imshow.svg)

### average inflammation

![average inflammation](img/inflammation-01-average.svg)

### maximum

![maximum](img/inflammation-01-maximum.svg)

### minimum

![minimum](img/inflammation-01-minimum.svg)

###  group plot

![group plot](img/inflammation-01-group-plot.svg)

## Exercises

### Plot Scaling

Why do all of our plots stop just short of the upper end of our graph?

<details>
<summary>Solution
</summary>
Because matplotlib normally sets x and y axes limits to the min and max of our data (depending on data range).
</details>

### Update your plotting code to automatically set a more appropriate scale. (Hint: you can make use of the max and min methods to help.)

<details>
<summary>Solution
</summary>

<pre>
# One method
axes3.set_ylabel('min')
axes3.plot(numpy.min(data, axis=0))
axes3.set_ylim(0,6)
</pre>

</details>

<details>
<summary>Solution
</summary>

<pre>
# A more automated approach
min_data = numpy.min(data, axis=0)
axes3.set_ylabel('min')
axes3.plot(min_data)
axes3.set_ylim(numpy.min(min_data), numpy.max(min_data) * 1.1)
</pre>

</details>

### Drawing Straight Lines

In the center and right subplots above, we expect all lines to look like step functions because non-integer value are not realistic for the minimum and maximum values. However, you can see that the lines are not always vertical or horizontal, and in particular the step function in the subplot on the right looks slanted. Why is this?

<details>
<summary>Solution
</summary>

Because matplotlib interpolates (draws a straight line) between the points. One way to do avoid this is to use the Matplotlib *drawstyle* option:

<pre>
import numpy
import matplotlib.pyplot

data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))

axes1 = fig.add_subplot(1, 3, 1)
axes2 = fig.add_subplot(1, 3, 2)
axes3 = fig.add_subplot(1, 3, 3)

axes1.set_ylabel('average')
axes1.plot(numpy.mean(data, axis=0), drawstyle='steps-mid')

axes2.set_ylabel('max')
axes2.plot(numpy.max(data, axis=0), drawstyle='steps-mid')

axes3.set_ylabel('min')
axes3.plot(numpy.min(data, axis=0), drawstyle='steps-mid')

fig.tight_layout()

matplotlib.pyplot.show()
</pre>

</details>

### Make Your Own Plot

Create a plot showing the standard deviation (numpy.std) of the inflammation data for each day across all patients.

<details>
<summary>Solution
</summary>


<pre>
std_plot = matplotlib.pyplot.plot(numpy.std(data, axis=0))
matplotlib.pyplot.show()
</pre>

</details>

### Moving Plots Around

Modify the program to display the three plots on top of one another instead of side by side.


<details>
<summary>Solution
</summary>

<pre>
import numpy
import matplotlib.pyplot

data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

# change figsize (swap width and height)
fig = matplotlib.pyplot.figure(figsize=(3.0, 10.0))

# change add_subplot (swap first two parameters)
axes1 = fig.add_subplot(3, 1, 1)
axes2 = fig.add_subplot(3, 1, 2)
axes3 = fig.add_subplot(3, 1, 3)

axes1.set_ylabel('average')
axes1.plot(numpy.mean(data, axis=0))

axes2.set_ylabel('max')
axes2.plot(numpy.max(data, axis=0))

axes3.set_ylabel('min')
axes3.plot(numpy.min(data, axis=0))

fig.tight_layout()

matplotlib.pyplot.show()
</pre>

</details>
