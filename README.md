# Tri-Branch-Vein-Patttern-Classification-For-Security
Finger vein recognition employs vein patterns on the finger palmar side in identity
authentication. The vein pattern is generally captured by the near-infrared light, as
the light can be intensively absorbed by the hemoglobin in the vein but easily
transmitted through other finger tissues. As an internal physiological
characteristic, finger vein has higher security over other external biometric traits
(e.g., face and fingerprint) owing to difficulty in copy or steal the trait.
In finger vein recognition, the existing feature extraction methods can be classified
into two groups, i.e., non-vein pattern based methods and vein pattern based
methods.

We will be using vein pattern methods. The following are the types:
1. Gray Value Based Methods:The vein pattern extraction methods were
developed based on the imaging characteristic of finger vein that the gray value of
vein point is lower than its neighbor non-vein points
2. Curvature Value Based Methods: There are four typical methods in this kind,
i.e., maximum curvature point, adaptive curve transformation, anatomy structure
analysis-based vein extraction (ASAVE) and mean curvature.
3. Convolution Response Based Methods: Gabor filters are used for vein pattern
extraction, in which the Gabor templates were designed firstly, and then the
convolution response values of the templates on finger vein image were employed
to detect the vein pattern.

The vein structure near the bifurcation point of vein pattern, named the tri-branch
vein structure, is explored and employed to improve the performance of template
matching by the proposed user-specific threshold based filter framework.

# Proposed methodology

The bifurcation point and its three local vein branches are powerful in the
assistance to the template matching. We name one bifurcation point and its three
local vein branches as the tri-branch vein structure. The structure will be extracted
from the vein pattern and used to assist the template matching.
In addition, to deeply explore the discrimination of the structure, the structure
should be used independent of other vein points.
1)The tri-branch vein structure is used in the first level of the framework to filter
the imposters and give the candidates for the probe.
2)The user-specific thresholds, not one common threshold, are used in filtering.
3)The reasons for using the tri-branch vein structure, instead of the whole vein
pattern, in the first level of the framework are twofold.

Obviously, the tri-branch vein structure spends less time cost and space cost than
the whole vein pattern in matching. More importantly, the orientation of branches
and the angles between two branches in one structure, and the distribution of
multiple structures in vein patterns vary largely in impostor vein patterns.

# WORKING PRINCIPLE

Two key points involved in execution:
1. How to define and extract the tri branch vein structure
2. How to define user specific threshold
Tri branch vein structure extraction:

1. Thinning and denoising:
The single pixel wide vein network is extracted front the vein network by
the morphological vein thinning operation.In the vein network, the intersection of the burr and vein branch can be
mistakenly seen as the bifurcation point. We detect and remove the burr based on its length, as the burr is much
shorter than the real vein branch.

2. Bifurcation detection:
The switching number between 0 and 1 in the eight neighbor points of the
bifurcation is six. Based on this, the bifurcation detection method is designed. Assuming the current point and its eight neighbor points are denoted by p(x,y) and P = {p1, p2, . . . , p8}respectively. The point p(x, y) is seen as a bifurcation, if Ns is equal to 6, which is defined as follows:

3. Branch Tracking:
Three nonzero neighbor points can be detected for one bifurcation
point, and these neighbors are the initial points of three vein branches.Once the initial point is found, each local branch of the bifurcation
can be tracked point by point until its length is equal to 15 points.Based on the first three steps, the single-pixel wide tribranch vein
structure (i.e., the bifurcation and its local branches) is detected. The more robust multiple-pixel wide structure will be achieved by the
following one step.

4. Morphological dilation and dot product
The morphological dilation operation is performed on the single-pixel wide
tri-branch vein structure. The structuring element is a 8×8 matrix with element value 1. The dot product between the dilated structure and the whole vein pattern is conducted to obtain the map of tri-branch vein structures.

# User specific threshold based filter:
The tri-branch vein structure is employed to filter the imposters for the probe
image in the first level of the proposed framework, but the false rejection of
genuine image should be avoided as much as possible. Therefore, the minimum genuine similarity score of training images may be a
reasonable filter threshold. If the probe user has a lower similarity score with one enrolled user than the
minimum genuine score of the enrolled user, the probe is seen as imposter to the
enrolled user. If the similarity score is larger than the minimum genuine score, the probe may be
genuine to the enrolled user and will be further matched in the second level. Generally, a common threshold (i.e., the minimum genuine score of all users) is used for all enrolled users to filter the imposters. However, in a tri-branch vein structure based filter, it may be not a good choice.The main reason is that the genuine score of the structure varies largely from one
enrolled user to another. In detail, this kind of local structure is sensitive to the image quality and finger
displacement, which may cause very low genuine score. Considering that the importance of matching score output by each biometric trait
varies with the user, the user-specific weights are used to fuse multi-traits for
different users in a multibiometric system. Inspired by the user-specific weight, the user-specific threshold is learned and
used to filter the imposters in our framework. The minimum genuine score among multiple images of one enrolled user is used
as the threshold only for this user. The user-specific thresholds are learned from the training images.

Assuming there are N enrolled users in the database, and each enrolled user has m
training images.
1. In the training step, the similarities of any two images among m training images
are measured for each user, and the minimum value of C2m similarity scores will
be used as the threshold for each user.
2. Therefore, there are totally N thresholds for N enrolled users.
