pretrain_unet_3b_bceloss.ipynb 
the network is initialized with parameter trained on imagenet
trained on RGB for 120 epoch

withoutpretrain_unet_4b_bceloss_swith1234.ipynb 
trained on RGB-nDSM for 120 epoch

withpretrain_unet_4b_bceloss_swith1234.ipynb
the network is initialized with parameter trained on imagenet
trained on RGB-nDSM for 120 epoch


the code use this libray:
https://github.com/qubvel/segmentation_models.pytorch

for this line:
class UNet(nn.Module):
    def __init__(self, out_classes=2, up_sample_mode='conv_transpose',encoder_weights="None"):

when encoder_weights set to None, the network will initialized with random value

if did not pass the parameter encoder_weights, the libray will initialized the network with weights trained on imagenet.
the source code of the libary is in the following python file 
https://github.com/qubvel/segmentation_models.pytorch/blob/master/segmentation_models_pytorch/unet/model.py
at line 48, encoder_weights: str = "imagenet" (the default value is imagenet)


