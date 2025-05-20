# BDQ_PrivacyAR

## Dataset Link
https://www.kaggle.com/datasets/dasmehdixtr/two-person-interaction-kinect-dataset/data

Link to pretrained I3D-50 kinetics model which they use:
https://github.com/IBM/action-recognition-pytorch/releases/download/weights-v0.1/K400-I3D-ResNet-50-f32.pth.tar

Link to pretrained resnet50 on imagenet:
https://download.pytorch.org/models/resnet50-19c8e357.pth

degradNet.py = BDQ module \
budgetNet.py = 2d conv (likely privacy predictor) \
utilityNet.py = 3d conv (likely action predictor)

SBU dataset format:
path, (doesnt matter always 1), num_frames, privacy_attribute, action attributes
13 number of privacy classes
8 number of action classes

in budgetNet.py ResNet class, num_classes=13 corresponds to privacy classes\
in utilityNet.py ResNet class, num_classes=8 corresponds to action classes\
in utils.py line 179 "-2" is alpha parameter defined in section 4.2. This is specific to SBU