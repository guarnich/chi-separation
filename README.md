#  chi-separation toolbox (*&chi;*-separation, x-separation)

* ⭐ New version of the toolbox is now available for test! Don't hesitate to contact us for bugs and feedbacks: snu.list.software@gmail.com 
* ⭐ This toolbox is developed for in-vivo human 3T datasets. Other field stengths, high resolution ex-vivo or nonhuman datasets (< 0.6 mm) are not fully tested and may require additional processing. 7T processing will be updated soon. 
* ⭐ E-mail us if you need data processing other than in-vivo human 3T datasets. We may be able to help you with scan protocol and processing. 
* ⭐ If you have both GRE and SE data, you have options for conventional optimization (MEDI, iLSQR) and neural network (chi-sepnet-R2', better quality). 
* ⭐ If you only have GRE data, neural network (chi-sepnet-R2*) will deliver high quality chi-separation maps.
* ⭐ Neural networks can process resolution > 0.6 mm. This makes high resolution ex-vivo or rodent data processing difficult if you only have GRE data.

* A toolbox for magnetic susceptibility source separation (**_&chi;_-separation or chi-separation; H. Shin et al., Neuroimage, 2021**). 

* The *&chi;*-separation toolbox includes the following features:
  - DICOM/NIFTI data compatibility
  - **QSMnet**: Quantitative susceptibility mapping (QSM) reconstruction algorithm based on deep neural network (QSMnet; J. Yoon et al., Neuroimage, 2018)
  - **_&chi;_-separation using _R_<sub>2</sub>' (or _R_<sub>2</sub>\* )**: Magnetic susceptibility source separation algorithms based on convex optimization (*&chi;*-separation; H. Shin et al., Neuroimage, 2021) that share similar contrasts and optimization parameters with either MEDI+0 (Liu et al., MRM, 2018) or iLSQR (Li et al., Neuroimage, 2015) algorithms. The toolbox also provides the option to use pseudo *R*<sub>2</sub> map if *R*<sub>2</sub> measurement is not availabe (using *R*<sub>2</sub>' is reconmmanded for accurate estimation).
  - **_&chi;_-sepnet using _R_<sub>2</sub>' (or _R_<sub>2</sub>\* )**: A U-Net-based neural network that reconstructs COSMOS-quality *&chi;*-separation using *R*<sub>2</sub>' and phase. In case *R*<sub>2</sub> is not measured, another neural network is trained to estimate *&chi;*-separation maps from *R*<sub>2</sub>\* and phase.
  - The toolbox also supports phase preprocessing (e.g. phase unwrapping and background removal) powered by MEDI, STI Suite, SEGUE, and mritools toolboxs (see the Chisep_script.m file for details). 

* Last update: June-11-2024 (Sooyeon Ji, Hyeong-Geol Shin, Jun-Hyeok Lee, Minjun Kim, Kyeongseon Min)


## Requirements
* Common
  - MATLAB (tested in R2019a-R2021a. Toolbox will fail any version before R2019a.)

* Additional
  - For QSMnet and *&chi;*-sepnet, Deep Learning MATLAB Toolbox Converter for ONNX Model Format (https://www.mathworks.com/matlabcentral/fileexchange/67296-deep-learning-toolbox-converter-for-onnx-model-format)
  - For DICOM/NIFTI read and phase processing, see https://www.dropbox.com/sh/3zafav50bfnruuu/AABVVYpdsznsRXKy8YKK4ybla?dl=0

## Recommendation for acquisitoin 
* Multiecho GRE data for in-vivo
  - TR = 33 ms; TE1 = 5 ms; Echo spacing = 6 ms; Number of echoes = 5; flip angle = 15° Matrix size (AP LR HF) = 256 x 176 x 144 Resolution = isotropic 1 mm  Parallel imaging factor = 2; elliptical k-space shutter  Acquisition time = 6 mins. 
  - Follow QSM consensus paper (https://doi.org/10.1002/mrm.30006)
* Multiecho SE data for in-vivo
  - TBA
* Multiecho GRE data for high resolution ex-vivo
  - Highly recommend to acquire multi-orientation data (relative to B0).

## Reference
* H. Shin, J. Lee, Y. H. Yun, S. H. Yoo, J. Jang, S.-H. Oh, Y. Nam, S. Jung, S. Kim, F. Masaki, W. Kim, H. J. Choi, J. Lee. *&chi;*-separation: Magnetic susceptibility source separation toward iron and myelin mapping in the brain. Neuroimage, 2021 Oct; 240:118371.
* Please refer to [[link](https://github.com/SNU-LIST/chi-separation/blob/main/LIST_OF_PAPERS.md)]


## Contacts
* snu.list.software@gmail.com
* sin4109@gmail.com (Hyeong-Geol Shin, PhD)
