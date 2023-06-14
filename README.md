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
