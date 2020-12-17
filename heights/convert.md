### Converting a Dictionary to a Data Frame
Here is a dictionary I created with different country's average male and female height data from 2014-2019.


```python
heights = {
    'sex':['male', 'male', 'male', 'male', 'male', 'male', 'male', 'male', 'female', 'female', 'female', 'female', 'female', 'female', 'female', 'female'],
    'country':['Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico', 'Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico'],
    'height':[177.8, 178, 183.4, 169.6, 172.7, 167.1, 179, 172, 164.6, 157, 169.4, 158.2, 159, 154.2, 165, 159]}

print(heights)
```

    {'sex': ['male', 'male', 'male', 'male', 'male', 'male', 'male', 'male', 'female', 'female', 'female', 'female', 'female', 'female', 'female', 'female'], 'country': ['Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico', 'Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico'], 'height': [177.8, 178, 183.4, 169.6, 172.7, 167.1, 179, 172, 164.6, 157, 169.4, 158.2, 159, 154.2, 165, 159]}


As you can see, this does not convey my data in a readable way. To make this look better, I converted it to a Data Frame, set the index as Country, and pivoted the table to make the columns Sex and the values Height.


```python
import pandas as pd

world_heights = pd.DataFrame(heights)
world_heights.index = world_heights['country'] ; del world_heights['country']
world_heights = world_heights.pivot(columns='sex', values='height')
print(world_heights)
```

    sex                 female   male
    country                          
    Dominican Republic   159.0  172.7
    Ecuador              154.2  167.1
    Ireland              165.0  179.0
    Italy                164.6  177.8
    Kenya                158.2  169.6
    Mexico               159.0  172.0
    Montenegro           169.4  183.4
    Romania              157.0  178.0


Now this is much more readable! I can more easily find the values I want and [visualize](visual.md) the data.
