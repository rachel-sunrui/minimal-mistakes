---
title: 'Coregister coordinate between brainstorm and curry'
date: 2020-10-05
permalink: /posts/2020/10/curry_bs/
categories:
  - Tools
---


### Export MRI from Brainstorm and import to Curry
1. Select mirror when importing the .nii MRI into Curry
2. Read the fiducial in Brainstorm in MRI coordinates. Load fiducial into the localizer in Curry coordinate *Image data RAS*. Then in Curry, select localizer --> save and use as image data landmarks.



### Import sEEG locations from Brainstorm to Curry
1. Export sEEG to file in .res format.

Matlab scripts: brainstorm to curry
```
curryPos = bsPos;
curryPos(:,1) = -bsPos(:,2);
curryPos(:,2) = bsPos(:,1);
curryPos = curryPos * 1000;
```

2. In Curry localziter, open the .res file in *PAN* coordinate.