# Car detection - YOLO

許多想法都在兩篇YOLO論文中有所描述： [Redmon et al., 2016](https://arxiv.org/abs/1506.02640) 和 [Redmon and Farhadi, 2016](https://arxiv.org/abs/1612.08242) 。

- **Problem Statement  :** 
以自駕車做為模擬情境，我們需要一個系統透過鏡頭來去偵測前方的車輛，數據來自 [drive.ai](https://www.drive.ai/)

**將所有這些圖像收集到一個文件夾中，並通過在找到的每輛車周圍繪製邊界框來標記它們。這是你的邊界框的樣子的一個例子。**
![box_label](https://github.com/s90210jacklen/YOLO-object-detection/blob/master/nb_images/box_label.png)
