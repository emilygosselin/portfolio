### Making Min and Max Statements
The last thing I wanted to do with my World Heights Data Frame is make statements about which countries had the shortest and tallest people. To do this, I used the following code...


```python
tfh = combined_wh['female'].max()
tfhc = combined_wh[combined_wh['female'] == tfh].index.values

tmh = combined_wh['male'].max()
tmhc = combined_wh[combined_wh['male'] == tmh].index.values

print('The country with the tallest average female height from 2012 to 2019 is ' + tfhc + ' with the average female height being ' + str(tfh) + ' cm')
print('The country with the tallest average male height from 2012 to 2019 is ' + tmhc + ' with the average male height being ' + str(tmh) + ' cm')
```

<img src='th1.png' width='1100'/>


```python
sfh = combined_wh['female'].min()
sfhc = combined_wh[combined_wh['female'] == sfh].index.values

smh = combined_wh['male'].min()
smhc = combined_wh[combined_wh['male'] == smh].index.values

print('The country with the shortest average female height from 2012 to 2019 is ' + sfhc + ' with the average female height being ' + str(sfh) + ' cm')
print('The country with the shortest average male height from 2012 to 2019 is ' + smhc + ' with the average male height being ' + str(smh) + ' cm')
```

<img src='sh1.png' width='1100'/>

This code is especially useful for my data because even if I decide to update by Data Frame at some point, I will not need to change the code to get the tallest and shortest heights and countries.
