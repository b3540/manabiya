MANABIYA ハンズオン 資料
========

このリポジトリは、[MANABIYA](https://manabiya.tech/) で開催するハンズオンイベント
『[本気で機械学習やる人のためのハンズオン ～教師データ作成から学習・性能評価まで～](https://twitter.com/MANABIYA_tech/status/973078689540923392)』
のためのハンズオン用 notebook および資料です。

手順
---------------

### 1. SageMaker の Notebook インスタンス

SageMaker のコンソールを開き、ノートブックインスタンスを作成・開始・オープンする。 

### 2. 初期スクリプト実行

Jupyter のターミナルを開き、以下のコマンドを順次実行する：

```sh
sh-4.2$ cd SageMaker/
sh-4.2$ pwd
/home/ec2-user/SageMaker
sh-4.2$ git clone https://github.com/antimon2/manabiya.git
Cloning into 'manabiya'...
 : 《中略》
sh-4.2$ git clone https://github.com/antimon2/models.git
Cloning into 'models'...
 : 《中略》
sh-4.2$ cd models
sh-4.2$ git status
On branch manabiya
Your branch is up-to-date with 'origin/manabiya'.
sh-4.2$ cd ../manabiya
sh-4.2$ curl -O http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 72.9M  100 72.9M    0     0  72.9M      0  0:00:01  0:00:01 --:--:-- 41.9M
sh-4.2$ tar xzf ssd_mobilenet_v1_coco_2017_11_17.tar.gz
sh-4.2$ 
```

### 3. データセットを取得

ハンズオン用に講師が作成したデータセット一式を取得します。このデータセットには以下が含まれています。

* 花札の画像
* 画像のどこにどの種類の札が写っているかを記したアノテーション（教師データ）
    * 単純なBounding Boxではなく、花札の絵の部分を切り取るようなPolygonのアノテーションになっています
    
Jupyter のターミナルで、以下のコマンドを実行：

```sh
sh-4.2$ cd /home/ec2-user/SageMaker/manabiya
sh-4.2$ wget https://s3-us-west-2.amazonaws.com/sagemaker-krs-manabiya/data-manabiya.tar.gz
sh-4.2$ tar xzf data-manabiya.tar.gz
sh-4.2$ 
```

※このデータセットは予告なく削除または更新する場合があります。また利用はハンズオン内にとどめてください。


### 4. notebook 実行

指示に従って `.ipynb` ファイルを順次開き、上から順に実行する。

+ Step1_DataConvert.ipynb
+ Step2_Train.ipynb
+ Step3_Detect.ipynb

