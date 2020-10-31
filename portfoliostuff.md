```python
import pandas as pd
import matplotlib.pyplot as plt
```


```python
world_heights = {
    'sex':['male', 'male', 'male', 'male', 'male', 'male', 'male', 'male', 'female', 'female', 'female', 'female', 'female', 'female', 'female', 'female'],
    'country':['Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico', 'Italy', 'Romania', 'Montenegro', 'Kenya', 'Dominican Republic', 'Ecuador', 'Ireland', 'Mexico'],
    'height':[177.8, 178, 183.4, 169.6, 172.7, 167.1, 179, 172, 164.6, 157, 169.4, 158.2, 159, 154.2, 165, 159]}

wh = pd.DataFrame(world_heights)
wh.index = wh['country']
del wh['country']
wh = wh.pivot(columns='sex', values='height')
print(wh)
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



```python
wh.plot(kind='bar', color=['teal','salmon'])

plt.ylabel('height (cm)')
plt.title('Average Height of Males and Females 2014-2019')

plt.show()
```




    
![png](messing%20around_files/messing%20around_2_0.png)
    




```python
world_heights_2 = {
    'sex':['male', 'male', 'male', 'male', 'male', 'female', 'female', 'female', 'female', 'female'],
    'country':['Denmark', 'Norway', 'Serbia', 'Northern Ireland', 'England', 'Denmark', 'Norway', 'Serbia', 'Northern Ireland', 'England'],
    'height':[180.4, 179.7, 182, 175.3, 177.8, 167.2, 167.1, 166.8, 161.9, 163.3]}

wh2 = pd.DataFrame(world_heights_2)
wh2.index = wh2['country']
del wh2['country']
wh2 = wh2.pivot(columns='sex', values='height')
print(wh2)
```

    sex               female   male
    country                        
    Denmark            167.2  180.4
    England            163.3  177.8
    Northern Ireland   161.9  175.3
    Norway             167.1  179.7
    Serbia             166.8  182.0



```python
combined_wh = pd.concat([wh, wh2], axis=0)
print(combined_wh)
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
    Denmark              167.2  180.4
    England              163.3  177.8
    Northern Ireland     161.9  175.3
    Norway               167.1  179.7
    Serbia               166.8  182.0



```python
combined_wh.plot(kind='bar', color=['purple','pink'])

plt.ylabel('height (cm)')
plt.title('Average Height of Males and Females 2012-2019')

plt.show()
```




    
![png](messing%20around_files/messing%20around_5_0.png)
    




```python
tfh = combined_wh['female'].max()
tfhc = combined_wh[combined_wh['female'] == tfh].index.values

tmh = combined_wh['male'].max()
tmhc = combined_wh[combined_wh['male'] == tmh].index.values

print('The country with the tallest average female height from 2014 to 2019 is ' + tfhc + ' with the average female height being ' + str(tfh) + ' cm')
print('The country with the tallest average male height from 2014 to 2019 is ' + tmhc + ' with the average male height being ' + str(tmh) + ' cm')
```

    ['The country with the tallest average female height from 2014 to 2019 is Montenegro with the average female height being 169.4 cm']
    ['The country with the tallest average male height from 2014 to 2019 is Montenegro with the average male height being 183.4 cm']



```python
sfh = combined_wh['female'].min()
sfhc = combined_wh[combined_wh['female'] == sfh].index.values

smh = combined_wh['male'].min()
smhc = combined_wh[combined_wh['male'] == smh].index.values

print('The country with the shortest average female height from 2014 to 2019 is ' + sfhc + ' with the average female height being ' + str(sfh) + ' cm')
print('The country with the shortest average male height from 2014 to 2019 is ' + smhc + ' with the average male height being ' + str(smh) + ' cm')
```

    ['The country with the shortest average female height from 2014 to 2019 is Ecuador with the average female height being 154.2 cm']
    ['The country with the shortest average male height from 2014 to 2019 is Ecuador with the average male height being 167.1 cm']



```python

```
