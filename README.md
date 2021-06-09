# MEDICAL-ULTRASOUND-NERVE-SEGMENTATION-USING-DEEP-LEARNING-

Surgery can cause persistent pain and short-term discomfort. Anesthesia is injected
into patient’s body to reduce the pain. Regional Anesthesia (RA) is employed
when the surgery involves a local procedure. It involves injecting the anesthetic into
the nerve block as close as possible to the nerve. Ultrasound guided regional anesthesia
(UGRA) is the Regional Anesthesia technique of injecting the anesthetic in
required amounts to immobilize the region to be covered, using ultrasound images
of patients. This method is gaining wide attention because of its non invasive nature
and it offers an accurate information of the nerve structure around it. However,
because of the characteristics of high speckle noise and echo perturbations, it is challenging
to identify accurate location of the nerve and its structure around it even by
specialists. The development of a system for segmentation of nerve and identification
of nerve structure using ultrasound images can aid this task by avoiding any
discrepancy in providing anesthesia and hence eliminate any risk of severe damage
to the respective region of the body or side effects to the rest of the body.


#Proposed Model
During operations, it can be difficult for surgeons to avoid severing crucial nerves
because they look so much like other tissue. so with the help of this simple model ,
we tried to segment the nerve from muscle fibre and tissues.Since machine learning
algorithms proved less effective in segmentation of nerve images, so we proceeded
with Deep learning model. We researched many Convolutional neural networks out
of which we choose UNET with our own modifications for Semantic Segmentation
of nerve images.
# Architecture
A naive approach towards constructing a neural network architecture for this task
is to simply stack a number of convolutional layers (with same padding to preserve
dimensions) and output a final segmentation map. This directly learns a mapping
from the input image to its corresponding segmentation through the successive transformation
of feature mappings, however it’s quite computationally expensive to preserve
the full resolution throughout the network.
Also, in deep convolutional networks, earlier layers tend to learn low-level concepts
while later layers develop more high-level (and specialized) feature mappings.
In order to maintain expressiveness, we typically need to increase the number of
feature maps (channels) as we get deeper in the network.
This didn’t necessarily pose a problem for the task of image classification. Thus,
we could alleviate computational burden by periodically downsampling our feature
maps through pooling or strided convolutions (i.e. compressing the spatial resolution)
without concern. However, for image segmentation, we would like our model
to produce a full-resolution semantic prediction.
