### Visualizing World Height Data
After creating an organized and readable Data Frame, I can visualize the data from the table in a bar chart using the following code...


```
import matplotlib.pyplot as plt

wh.plot(kind='bar', color=['teal','salmon'])
plt.ylabel('height (cm)')
plt.title('Average Height of Males and Females 2014-2019')

plt.show()
```

<img src="wh bar plot.png" width="800"/>

This bar plot helps visualize the World Height data and we can start to analyze it.
