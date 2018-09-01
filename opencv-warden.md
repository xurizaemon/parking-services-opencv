# Detecting things with OpenCV

- Installed OpenCV binaries from https://github.com/jabelone/OpenCV-for-Pi
- Sample images: https://chris.bur.gs/images/8-stafford-20180901.tgz
- http://note.sonots.com/SciSoftware/haartraining.html#e134e74e tutorial

```
opencv_createsamples -info warden-fullbody.dat -vec warden-fullbody.vec -bg negative.txt -num 67
opencv_createsamples -info warden-head+torso.dat -vec warden-head+torso.vec -bg negative.txt -num 66
opencv_createsamples -info warden-bike.dat -vec warden-bike.vec -bg negative.txt -num 62
```

```
opencv_traincascade -data data/warden-bike -vec warden-bike.vec -bg negative.txt -numPos 62 -numNeg 69 -numStages 5 -featureType LBP
opencv_traincascade -data data/warden-head+torso -vec warden-head+torso.vec -bg negative.txt -numPos 66 -numNeg 69 -numStages 5 -featureType LBP
opencv_traincascade -data data/warden-fullbody -vec warden-fullbody.vec -bg negative.txt -numPos 62 -numNeg 67 -numStages 5 -featureType LBP
```
