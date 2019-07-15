# Car detection - YOLO

許多想法都在兩篇YOLO論文中有所描述： [Redmon et al., 2016](https://arxiv.org/abs/1506.02640) 和 [Redmon and Farhadi, 2016](https://arxiv.org/abs/1612.08242) 。

# 1 - Problem Statement
- **Problem Statement:** 
以自駕車做為模擬情境，我們需要一個系統透過鏡頭來去偵測前方的車輛，數據來自 [drive.ai](https://www.drive.ai/)

**將所有這些圖像收集到一個文件夾中，並通過在找到的每輛車周圍繪製邊界框來標記它們。以下是邊界框的一個例子。**
![box_label](https://github.com/s90210jacklen/YOLO-object-detection/blob/master/nb_images/box_label.png)

假使你希望YOLO識別出80個類別，則可以將類標籤以c表示為1到80之間的整數，或者表示為80維向量(80個數字)，其中只有一個類别為1，其餘為0; 在這個筆記本中，我們將使用兩種表示形式，具體取決於特定步驟哪個更方便。

**Note:** 由於YOLO模型的訓練計算成本非常高，因此這裡將加載預訓練的權重來使用在此應用。

# 2 - YOLO
