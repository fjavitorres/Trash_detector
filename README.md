# Trash_detector

 This AI is programmed to detect which dumpster an item belongs to. When an image is shown to the AI, the machine will detect if the item should be deposited in a blue dumpster (paper and cardboard), green dumpster (glass) or yellow dumpster (plastic and metal). 

![image](https://github.com/user-attachments/assets/4b603afa-0a10-404f-806b-fb3b5e0c76c3)

 ![image](https://github.com/user-attachments/assets/d9d36b0a-60ee-4d6d-95a3-cdd2ed6565ef) ![image](https://github.com/user-attachments/assets/4071cddb-b92b-487c-bba4-3309910be50b) ![image](https://github.com/user-attachments/assets/2c081937-b1f5-4d89-a715-60ab256a55f7)




## The Algorithm

The algorithm re-trains the ResNet-18 model by adapting its pre-trained weights to classify different types of waste and trash. ResNet-18’s residual blocks help the model learn effectively even with deeper networks. Transfer learning is used to update the model’s weights based on the new dataset of waste types, improving its ability to recognize various trash categories and to which dumpster they belong. Dependencies include PyTorch for training and ONNX for exporting the model, with Docker managing the training environment.

## Running this project

1. Setup your Jetson Nano and Install VScode
2. Connect Jetson Nano onto your computer hotspot. Write down your Jetson Nano IP address for later use
3. Connect your VScode to your Jetson Nano using Connect Host and ssh nvidia@IPAddress
4. Open the NVIDIA home folder
5. Open the terminal and use `cd jetson-inference/python/training/classification` do enter the needed directory
6. Use `NET=models/Final_project and DATASET=data/Final_project` to set NET and DATASET for later reference
7. Transfer the images from the laptop to VS Code.
8. Navigate into folder `cd jetson-inference/python/training/classification`
9. Run the model using `imagenet.py --model=$NET/resnet18.onx —-input_blob=input_0 - output_blob=output_0 —-labels=$DATASET/labels.txt input/IMAGE_NAME output/IMAGE_OUTPUT_NAME` Replace IMAGE_NAME with the name of your image and IMAGE_OUTPUT_NAME with the name of what you want the output image to be.
10. Enjoy running the trash detector model!
