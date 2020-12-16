### Importing and Visualizing MRI Data

To begin, we first import the necessary packages...


```python
import imageio
import matplotlib.pyplot as plt
```

Now we are going to read in the data file using imageio and take a look at which imaging technique was used...


```python
brain = imageio.imread('Anat001.20040930.142737.2.MPRAGE_T1_SAGITTAL.0080.dcm')
brain.meta['Modality']
```

<img src='mr.png' />

<p>&nbsp;</p>

Looks like this data is from magnetic resonance imaging, let's see what it looks like. To do this, we will use pyplot.imshow() with the parameter cmap='gray' to show the image in grayscale. We will also specify plt.axis('off') to view only the image.


```python
plt.imshow(brain_img, cmap='gray')
plt.axis('off')
plt.show()
```

<img src='mri.png' width=350 />

<p>&nbsp;</p>

This looks great! Next we will apply a mask to visualize the bright areas of the MRI, indicating fatty brain matter.
