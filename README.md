# Car detection - YOLO

許多想法都在兩篇YOLO論文中有所描述： [Redmon et al., 2016](https://arxiv.org/abs/1506.02640) 和 [Redmon and Farhadi, 2016](https://arxiv.org/abs/1612.08242) 。

# 1 - Problem Statement

以自駕車做為模擬情境，我們需要一個系統透過鏡頭來去偵測前方的車輛，數據來自 [drive.ai](https://www.drive.ai/)

**將所有這些圖像收集到一個文件夾中，並通過在找到的每輛車周圍繪製邊界框來標記它們。以下是邊界框(bounding box)的一個例子。**
![box_label](https://github.com/s90210jacklen/YOLO-object-detection/blob/master/nb_images/box_label.png)

假使你希望YOLO識別出80個類別，則可以將類標籤以c表示為1到80之間的整數，或者表示為80維向量(80個數字)，其中只有一個類别為1，其餘為0; 在這個筆記本中，我們將使用兩種表示形式，具體取決於特定步驟哪個更方便。

**Note:** 由於YOLO模型的訓練計算成本非常高，因此這裡將加載預訓練的權重來使用在此應用。

# 2 - YOLO
YOLO ("you only look once") 是一個相當受歡迎的演算法，因為它可以在real-time的應用上仍有很高的準確率。該演算法在圖像中"only looks once"(僅查看一次)，因為它只需要一次的forward propagation(前向傳播)通過網絡就能進行預測。而在經由non-max suppression之後，它然後將識別的物件與邊界框(bounding boxes)一起輸出。

- **2.1 - Model details**
