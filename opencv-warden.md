# Detecting things with OpenCV

- Installed OpenCV binaries from https://github.com/jabelone/OpenCV-for-Pi
- Sample images: https://chris.bur.gs/images/8-stafford-20180901.tgz
- http://note.sonots.com/SciSoftware/haartraining.html#e134e74e tutorial

    opencv_createsamples -info warden-fullbody.dat -w 40 -h 40 -vec warden-fullbody.vec
    opencv_createsamples -info warden-head+torso.dat -w 40 -h 40 -vec warden-head+torso.vec
    opencv_createsamples -info warden-fullbody.dat -w 40 -h 40 -vec warden-fullbody.vec

    opencv_traincascade -data data/warden-bike -vec warden-bike.vec -bg negative.txt -numPos 50 -numNeg 500 -numStages 14 -w 40 -h 40 -featureType LBP
    opencv_traincascade -data data/warden-fullbody -vec warden-fullbody.vec -bg negative.txt -numPos 50 -numNeg 500 -numStages 5 -w 40 -h 40 -featureType LBP
    opencv_traincascade -data data/warden-head+torso -vec warden-head+torso.vec -bg negative.txt -numPos 50 -numNeg 500 -numStages 5 -w 40 -h 40 -featureType LBP
