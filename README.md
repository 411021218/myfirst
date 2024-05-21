# Human Parsing

進入HP資料夾  
將要生成人體分割圖的圖片放置inputs資料夾  
執行  
```
python simple_extractor.py
python simple_extractor_lip.py
```

# MGD

進入MGD資料夾  
將要生成的圖片資料放在想要的分類資料夾  
這邊假設要做dresses，檔案名稱為000000  
在`MGD/assets/data/dresscode/dresses/images`放入圖片，檔名為000000_0.jpg  
在`MGD/assets/data/dresscode/dresses/im_sketch`放入繪圖  
在`MGD/assets/data/dresscode/dresses/keypoints`放入OpenPose生成的人體關鍵點  
在`MGD/assets/data/dresscode/dresses/label_maps`放入Human Parsing生成的人體分割圖  
在`MGD/assets/data/dresscode/test_stitchmap`放入Human Parsing生成的人體分割圖(lip格式)  
在`MGD/assets/data/dresscode/dresses/test_pairs_paireed.txt`放入要執行的檔名，格式為  
```
000000_0.jpg    000000_1.jpg
```
在`MGD/assets/data/dresscode/coar_captions.json`放入衣服描述，格式為  
```
{
  "000000": ["這裡放描述1", "這裡放描述2", "這裡放描述3"]
}
```
以上資料都齊全後  
在終端機輸入以下指令即可執行(此時位置為MGD資料夾)
```
python src/eval.py --category dresses
```

# 網站使用
進入各個這三個資料夾
執行
```
python manage.py runserver 8000
```
即可開啟網站
後面的port要用不同的

