### Aligning Photos using Markdown
When completing a course assignment, I came across the problem of aligning photos using Markdown. I wanted my photo on the right side but the default alignment is left...


```
<img src='chicken.jpg' width='200'>
```

<img src='chicken.jpg' width='200'>

<p>&nbsp;</p>

The **align** parameter can change the alignment of the photo to the right...


```
<img src='chicken.jpg' width='200' align='right'>
```

<img src='chicken.jpg' width='200' align='right'>

<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>

This was what I was initially trying to do, but I decided to experiment with a center alignment...


```
<img src='chicken.jpg' width='200' align='center'>
```

<img src='chicken.jpg' width='200' align='center'>

<p>&nbsp;</p>

I was shocked it did not work! In order to center align a photo you must ***wrap*** the code with the center alignment, like this...


```
<p align='center'>
    <img src='chicken.jpg' width='200'>
</p>
```

<p align='center'>
    <img src='chicken.jpg' width='200'>
</p>

<p>&nbsp;</p>

I hope this helped if you were unsure how to align photos in Markdown!
