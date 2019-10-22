# Description
アバターをブラウザで表示

# DB
```
room_name | model_path | background_path | sound_path | vmd_path |  subtitle_path
```
- プライマリキーは`room_name`
    - その関係上、`room_name`は日本語を含まないほうが望ましい
- すべてString
- `app.py`の`Entry`クラスで定義しているのでそちらも参照

# System
## RoomCreate
- room_nameなどを入力
- room_nameが使用可能か判定
- DBに保存
- Vstudio(?room_name=hogehoge)に遷移
- (できれば)ajaxでモデルをリアルタイム表示
- (できれば)編集パスワードもDBに保存

## Vstudio(?room_name)
- 録画開始ボタンを表示
- jsで録画＆録音
- 録画中はタイマーを表示
- 終わったらPythonで処理
- それか直接vmdを貼り付け
- vmdを得たらDBに保存

## Vroom(?room_name)
- DBからroom_nameに対応する各種データを取り出し
- それを使い, Three.jsでroomを表示

# todo
- app.py内のurlを動的に
- カメラ＆マイク
- qrコード