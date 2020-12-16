### Combining and Visualizing Two Data Frames
Some data may need to be appended as time goes on and more research is done. Below, there is a new Data Frame, world_heights2 containing height data from 2012, that I would like to add to my original World Heights Data Frame.

<img src='wh2 table.png' width='300'/>

To combine these Data Frames, I used pd.concat() with the axis=0 option to stack the two datasets...


```
combined_heights = pd.concat([world_heights, world_heights2], axis=0)
print(combined_heights)
```

<img src='combined wh table.png' width='300'/>

Now I have more data that I can visualize again using a bar chart...


```
combined_heights.plot(kind='bar', color=['purple','pink'])

plt.ylabel('height (cm)')
plt.title('Average Height of Males and Females 2012-2019')

plt.show()
```

<img src='combined wh plot.png' width='800'/>
