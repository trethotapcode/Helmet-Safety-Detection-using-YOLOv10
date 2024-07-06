# Helmet Safety Detection using YOLOv10
### In this project, I will build a program to detect whether employees are wearing safety helmets on the construction site. The model I will use is YOLOv10.
1. First of all, on the Colab shell, we need to clone YOLOv10 from public GitHub with the following code as [here](https://github.com/THU-MIG/yolov10.git):
    ```bash
    
    !git clone https://github.com/THU-MIG/yolov10.git

2. Then, download file  `best.pt` from my repository and upload it into your project on Colab `./content/yolov10`


3. Run this code to import all necessary libraries and install the Python package in *editable mode* from the current directory `.`:
```bash

    %cd yolov10
    !pip install -q -r requirements.txt
    !pip install -e .

```

4. Next, we start the model with the following command:
```python

    from ultralytics import YOLOv10
    MODEL_PATH = 'best.pt'
    model = YOLOv10(MODEL_PATH)

```

5. Create an IO folder, upload the `IMAGE_FILE` in *JPG, JPEG, PNG* format to Colab using the command `!gdown`:
```bash

    !gdown 'ID_IMAGE' -O './image/'

```


6. Predict with `IMAGE_FILE`
```python

    IMG_PATH = './image/IMAGE_FILE'
    result = model(source = IMG_PATH)[0]

```


7. Save and display prediction results
```python

    result.save('./image/sample_predict.jpg')
    
```



***Image before and after prediction:***

<img src="https://sotaville.com/wp-content/uploads/2024/03/su-dung-non-bao-ho-1.jpg" alt="Before" width="300" height="200">
<img src="https://i.imgur.com/WpMydSZ.jpg" alt="After" width="300" height="200">


***

 *- implemented by @wanghii*
