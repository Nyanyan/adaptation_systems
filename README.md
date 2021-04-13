# adaptation_systems
適応システム構成論(0AL5524)での課題を快適に行うためのスクリプトたち
# 動作環境
・Python3(Python3.7及びPython3.8での正常な動作を確認しています)  
・ターミナルもしくはコマンドプロンプトから`g++`がたたけること(Windowsでたたけない場合はMinGWをインストールしてください)
# 使い方
## テストケースの生成
```
python make_dataset.py
```
デフォルトではテストケースが50個生成されるようになっています.  
生成するテストケースの数を変えたい場合は`make_dataset.py`内の`datasets`の値を変えてください.  
テストケースは`in`というディレクトリ内にすべて吐き出されます(ディレクトリが生成されていない場合は自動で生成します)  
デフォルトではテストケース数50, 各引数の値は-1~1になるように乱数を発生させています.  
変更したい場合はスクリプト内のコメントアウトを参考に書き換えてください.(コマンドライン引数で指定できるようにしたいとは思っています)

## 課題1のジャッジ
`judge_task1.py`, `judge_task1_parallel.py`, 作成したソースコード, 生成したテストケースのディレクトリ(`in`)をすべて同じ階層に入れるようにして下さい.  
```
python judge_task1.py
```

並列実行したい場合はこちら
```
python judge_task1_parallel.py
```
これらを叩くと作成したソースコードのファイル名の入力が求められるので入力し, 実行してください.  
スコアの算出は各テストケースでのグループ0とグループ1の差の絶対値を取り, すべて足しています.  
そのため, 最終的に出てきたスコアが低ければ低いほどいいです.  

### 注意点
・ジャッジスクリプトでは途中出力があると正しくジャッジできないので最終解のみ出力するようにして実行してください.  
・`judge_task1_parallel.py`ではTLEの判定ができません.  
