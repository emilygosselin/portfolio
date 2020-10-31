### Combining and Visualizing Two Data Frames
Some data may need to be appended as time goes on and more research is done. Below, there is a new Data Frame that I would like to add to my original World Heights Data Frame, containing height data from 2012. 

<img src='wh2 table.png' width='300'/>

To combine these Data Frames, I used the following code...


```
combined_wh = pd.concat([wh, wh2], axis=0)
print(combined_wh)
```

<img src='combined wh table.png' width='300'/>

Now I have more data that I can visualize again using a bar chart...


```
combined_wh.plot(kind='bar', color=['purple','pink'])

plt.ylabel('height (cm)')
plt.title('Average Height of Males and Females 2012-2019')

plt.show()
```

<img src='combined wh plot.png' width='800'/>
