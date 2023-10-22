[English](../../README.md) | [简体中文](../../README_ch.md) | [हिन्दी](./README_हिन्द.md) | 日本語 | [한국인](./README_한국어.md) | [Pу́сский язы́к](./README_Ру́сский_язы́к.md)

<p align="center">
<img src="../PaddleOCR_log.png" align="middle" width = "600"/>
<p align="center">
<p align="left">
    <a href="./LICENSE"><img src="https://img.shields.io/badge/license-Apache%202-dfd.svg"></a>
    <a href="https://github.com/PaddlePaddle/PaddleOCR/releases"><img src="https://img.shields.io/github/v/release/PaddlePaddle/PaddleOCR?color=ffa"></a>
    <a href=""><img src="https://img.shields.io/badge/python-3.7+-aff.svg"></a>
    <a href=""><img src="https://img.shields.io/badge/os-linux%2C%20win%2C%20mac-pink.svg"></a>
    <a href=""><img src="https://img.shields.io/pypi/format/PaddleOCR?color=c77"></a>
    <a href="https://pypi.org/project/PaddleOCR/"><img src="https://img.shields.io/pypi/dm/PaddleOCR?color=9cf"></a>
    <a href="https://github.com/PaddlePaddle/PaddleOCR/stargazers"><img src="https://img.shields.io/github/stars/PaddlePaddle/PaddleOCR?color=ccf"></a>
</p>


## はじめに

PaddleOCRは、ユーザーがより良いモデルを訓練し、実践に応用できるように、多言語に対応し、素晴らしく先導的で実用的なOCRツールを作成することを目標としています。

<div align="center">
    <img src="https://user-images.githubusercontent.com/50011306/187821591-6cb09459-fdbf-4ad3-8c5a-26af611c211d.png" width="800">
</div>
<div align="center">
    <img src="../imgs_results/PP-OCRv3/en/en_4.png" width="800">
</div>
<div align="center">
    <img src="../imgs_results/ch_ppocr_mobile_v2.0/00006737.jpg" width="800">
</div>

## 📣 最新アップデート

- **🔥2023.8.7 PaddleOCR [release/2.7](https://github.com/PaddlePaddle/PaddleOCR/tree/release/2.7)をリリースしました**    
  - [PP-OCRv4](.././doc/doc_ch/PP-OCRv4_introduction.md)をリリースしました、モバイル版とサーバー版をサポートしています。    
    - PP-OCRv4-mobile：速度が同等の場合、中国語での認識精度はPP-OCRv3に比べて4.5%向上し、英語での性能は10%向上し、80言語の多言語モデルの平均認識精度は8%以上向上します。
    - PP-OCRv4-server：現在最高精度のOCRモデルをリリースしました。中国語と英語のシーンでの検出モデルの精度が4.9%向上し、認識モデルの精度が2%向上しました。    
        [クイックスタート](../../doc/doc_en/quickstart_en.md)を参照することで、一行のコマンドで使用可能です。同時に、モデルの訓練、推論、高性能デプロイの全過程もPaddleXの[一般的な産業向けOCRソリューション](https://aistudio.baidu.com/aistudio/modelsdetail?modelId=286)で少ないコードで完了できます。    
  - [PP-ChatOCR](https://aistudio.baidu.com/aistudio/modelsdetail?modelId=332)をリリースしました。PP-OCRモデルとERNIE LLMを使用した一般的なのキー情報抽出を行えます。    
- 🔨**2022.11 [4つの最先端アルゴリズム](../doc_ch/algorithm_overview_en.md)の実装を追加しました**：テキスト検出 [DRRG](../doc_en/algorithm_det_drrg_en.md)、テキスト認識 [RFL](../doc_en/algorithm_rec_rfl_en.md)、超解像 [Text Telescope](../doc_en/algorithm_sr_telescope_en.md)、手書き数式の認識 [CAN](../doc_en/algorithm_rec_can_en.md)    
- **2022.10 [最適化されたJS版PP-OCRv3モデル](../../deploy/paddlejs/README.md)をリリースしました** モデルサイズ4.3M、推論時間が8倍速く、すぐに使用できるウェブデモがついています。    
- 💥 **ライブ再生：PP-StructureV2最適化戦略の紹介**。WeChatを使って[下のQRコード](#Community)をスキャンし、PaddlePaddle公式アカウントをフォローし、アンケートに記入してWeChatグループに参加してください。録画リンクと20GのOCR学習資料（PDFからWordに変換する方法や、様々な分野の10モデルなどを含む）を入手できます。

- **🔥2022.8.24 リリース PaddleOCR [release/2.6 ](https://github.com/PaddlePaddle/PaddleOCR/tree/release/2.6)**
  -  [PP-Structurev2](../../ppstructure/)をリリースしました。機能と性能は全面的にアップグレードされ、中国誤に対応しています。新たに[Layout Recovery](../../ppstructure/recovery)と**一行のコマンドでPDFをWordに変換する**機能をサポートしています。        
  - [layout analysis](../../ppstructure/layout) の最適化：モデルのストレージが95%削減され、速度は11倍に増加し、平均CPU時間コストは41msになりました。
  - [Table Recognition](../../ppstructure/table) の最適化：3つの最適化戦略を設計し、同等の速度の下でモデルの精度が6%改善されました。    
  - [Key Information Extraction](../../ppstructure/kie) の最適化：視覚から独立したモデル構造を設計し、semantic entity recognitionの精度が2.8%向上し、関係抽出の精度が9.1%向上しました。        

- **🔥2022.8 リリース [OCR scene application collection](../../applications/README_en.md)**
   - 7セグメント文字、液晶画面、ナンバープレート、手書き認識モデル、高精度 SVTR モデルなど、**9つの分野に特化したモデル**をリリースしました。これらは一般的な産業、製造業、金融業、交通業界での主要な分野特化型OCRへの応用方法に対応しています。

- **2022.8 [8つの最先端アルゴリズム](doc/doc_en/algorithm_overview_en.md)の実装を追加しました**        
  - テキスト検出：[FCENet](../../doc/doc_en/algorithm_det_fcenet_en.md), [DB++](../../doc/doc_en/algorithm_det_db_en.md)        
  - テキスト認識：[ViTSTR](../../doc/doc_en/algorithm_rec_vitstr_en.md), [ABINet](../../doc/doc_en/algorithm_rec_abinet_en.md), [VisionLAN](../../doc/doc_en/algorithm_rec_visionlan_en.md), [SPIN](../../doc/doc_en/algorithm_rec_spin_en.md), [RobustScanner](../../doc/doc_en/algorithm_rec_robustscanner_en.md)        
  - Table Recognition：[TableMaster](../../doc/doc_en/algorithm_table_master_en.md)   

- **2022.5.9 PaddleOCR [release/2.5](https://github.com/PaddlePaddle/PaddleOCR/tree/release/2.5)をリリースしました**     
    -  [PP-OCRv3](../doc_en/ppocr_introduction_en.md#pp-ocrv3)をリリースしました。同等の速度で、中国語での精度はPP-OCRv2に比べて5%、英語での精度は11%、80言語の多言語モデルの平均認識精度は5%以上改善しました。
    -  [PPOCRLabelv2](../../PPOCRLabel)をリリースしました。表認識タスク、キー情報抽出タスク、不規則なテキスト画像の注釈機能を追加しました。        
    - インタラクティブな電子ブック[*"Dive into OCR"*](../doc_en/ocr_book_en.md)をリリースしました。これはOCRにおける全スタック技術の最先端理論とコードデモをカバーしています。        
- 詳しくは[こちら](../doc_en/update_en.md)をご覧ください。


## 🌟 PaddleOCRとは？

PaddleOCRは、OCRに関連するさまざまな最先端のアルゴリズムをサポートしています。
産業用の特化モデル/ソリューション [PP-OCR](../doc_en/ppocr_introduction_en.md) や [PP-Structure](../../ppstructure/README.md) および [PP-ChatOCR](https://aistudio.baidu.com/aistudio/projectdetail/6488689)を開発し、データ生成からモデル訓練、圧縮、推論、デプロイまでの一連のプロセスを整備しています。  

<div align="center">
    <img src="https://user-images.githubusercontent.com/50011306/195771471-fad5eb1d-190d-4a7b-8b0c-0433fb32445f.png">
</div>

> ドキュメントチュートリアルの「クイックデモ」から始めることをお勧めします  
  
  
## ⚡ クイックデモ
  
- ウェブでのオンラインデモ  
    - PP-OCRv4 のオンラインデモ：https://aistudio.baidu.com/application/detail/7658  
    - PP-ChatOCR のオンラインデモ：https://aistudio.baidu.com/application/detail/7709  
  
- 一行のコードでの簡単な利用方法：[クイックスタート（中国語/英語/多言語/ドキュメント分析)](../../doc/doc_en/quickstart_en.md)  
- Paddle AI パッケージ（PaddleX）でのトレーニング、推論、高性能デプロイのデモ：  
    - PP-OCRv4：https://aistudio.baidu.com/projectdetail/paddlex/6796224  
    - PP-ChatOCR：https://aistudio.baidu.com/projectdetail/paddlex/6796372  
- モバイルデモ：[インストールデモ](https://ai.baidu.com/easyedge/app/openSource?from=paddlelite)(EasyEdgeとPaddle-Liteを使い、iOSとAndroidシステムをサポートします。) 

<a name="本"></a>

## 📚 電子書籍：*OCRに入る*
- [OCRに没入](../doc_en/ocr_book_en.md)

<a name="コミュニティ"></a>

## 👫コミュニティー

他国の開発者の方は [PaddleOCR Discussions](https://github.com/PaddlePaddle/PaddleOCR/discussions) を国際的なコミュニティ プラットフォームとして使用します。みなさんのアイデアや質問がある場合、ここで英語で話し合うことができます。

<a name="対応中国機種一覧"></a>

## 🛠️ シリーズ モデル式一覧

| モデル紹介                                           | モデル名                   | 推奨のシーン | 検出モデル                                             | 認識モデル                                           |
| ------------------------------------------------------------ | ---------------------------- | ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 日本語超軽量 PP-OCRv3 モデル(14.8M) | japan_PP-OCRv3_xx | モバイル & サーバー |[推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_infer.tar)/[トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/Multilingual_PP-OCRv3_det_distill_train.tar) |[推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/japan_PP-OCRv3_rec_infer.tar)/[トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/multilingual/japan_PP-OCRv3_rec_train.tar) |
| 英語超軽量PP-OCRv3モデル（13.4M） | en_PP-OCRv3_xx | モバイル & サーバー | [推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_infer.tar) / [トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_det_distill_train.tar) | [推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_infer.tar) / [トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/english/en_PP-OCRv3_rec_train.tar) |
| 中国語と英語の超軽量 PP-OCRv3 モデル（16.2M）    | ch_PP-OCRv3_xx          | モバイル & サーバー | [推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_det_infer.tar) / [トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_det_distill_train.tar) | [推論モデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_infer.tar) / [トレーニングモデル](https://paddleocr.bj.bcebos.com/PP-OCRv3/chinese/ch_PP-OCRv3_rec_train.tar) |


- その他のモデルのダウンロード (多言語を含む) については、[PP-OCR シリーズ モデルのダウンロード] (../doc_en/models_list_en.md)をご参照ください。
- 新しい言語のリクエストについては、 [新しい言語_リクエストのガイドライン](#language_requests)を参照してください。
- 構造文書分析モデルについては、[PP-Structure models](../../ppstructure/docs/models_list_en.md)をご参照ください。

<a name="チュートリアル"></a>

## 📖 チュートリアル

- [環境の準備](../doc_en/environment_en.md)
- [PP-OCR 🔥](../doc_en/ppocr_introduction_en.md)
    - [クイックスタート](../doc_en/quickstart_en.md)
    - [Model Zoo](../doc_en/models_en.md)
    - [トレーニング モデル](../doc_en/training_en.md)
        - [テキスト検出](../doc_en/detection_en.md)
        - [テキスト認識](../doc_en/recognition_en.md)
        - [テキスト方向の分類](../doc_en/angle_class_en.md)
    - モデル圧縮
        - [モデルの量子化](./deploy/slim/quantization/README_en.md)
        - [モデルの剪裁](./deploy/slim/prune/README_en.md)
        - [知識の蒸留](../doc_en/knowledge_distillation_en.md)
    - [推論と展開](./deploy/README.md)
        - [Python 推論](../doc_en/inference_ppocr_en.md)
        - [C++ 推論](./deploy/cpp_infer/readme.md)
        - [サービング](./deploy/pdserving/README.md)
        - [モバイル](./deploy/lite/readme.md)
        - [Paddle2ONNX](./deploy/paddle2onnx/readme.md)
        - [PaddleCloud](./deploy/paddlecloud/README.md)
        - [Benchmark](../doc_en/benchmark_en.md)  
- [PP-Structure 🔥](../../ppstructure/README.md)
    - [クイックスタート](../../ppstructure/docs/quickstart_en.md)
    - [Model Zoo](../../ppstructure/docs/models_list_en.md)
    - [トレーニング モデル](../doc_en/training_en.md)  
        - [レイアウト分析](../../ppstructure/layout/README.md)
        - [表認識](../../ppstructure/table/README.md)
        - [キー情報抽出](../../ppstructure/kie/README.md)
    - [推論と展開](./deploy/README.md)
        - [Python 推論](../../ppstructure/docs/inference_en.md)
        - [C++ 推論](./deploy/cpp_infer/readme.md)
        - [サービング](./deploy/hubserving/readme_en.md)
- [アカデミックアリゴリズム](../doc_en/algorithm_overview_en.md)
    - [テキスト検出](../doc_en/algorithm_overview_en.md)
    - [テキスト認識](../doc_en/algorithm_overview_en.md)
    - [エンド・ツー・エンド OCR](../doc_en/algorithm_overview_en.md)
    - [表認識](../doc_en/algorithm_overview_en.md)
    - [キー情報抽出](../doc_en/algorithm_overview_en.md)    
    - [PaddleOCR に新しいアルゴリズムを追加する](../doc_en/add_new_algorithm_en.md)
- データの注釈と合成
    - [半自動注釈ツール: PPOCRLabel](./PPOCRLabel/README.md)
    - [データ合成ツール: Style-Text](./StyleText/README.md)
    - [その他のデータ注釈ツール](../doc_en/data_annotation_en.md)
    - [その他のデータ合成ツール](../doc_en/data_synthesis_en.md)
- データセット
    - [一般OCRデータセット(中国語/英語)](../doc_en/dataset/datasets_en.md)
    - [HandWritten_OCR_Datasets(中国語)](../doc_en/dataset/handwritten_datasets_en.md)
    - [各種OCRデータセット(多言語対応)](../doc_en/dataset/vertical_and_multilingual_datasets_en.md)
    - [レイアウト分析](../doc_en/dataset/layout_datasets_en.md)
    - [表認識](../doc_en/dataset/table_datasets_en.md)
    - [キー情報抽出](../doc_en/dataset/kie_datasets_en.md)
- [コード構造](../doc_en/tree_en.md)
- [視覚化](#Visualization)
- [コミュニティ](#Community)
- [新言語のリクエスト](#language_requests)
- [よくある質問](../doc_en/FAQ_en.md)
- [参考文献](../doc_en/reference_en.md)
- [ライセンス](#LICENSE)

<a name="language_requests"></a>

## 🇺🇳 新しい言語リクエストのガイドライン

**新言語モデルをリクエスト**したい場合、[多言語モデルのアップグレードへの投票](https://github.com/PaddlePaddle/PaddleOCR/discussions/7253)で投票してください。投票結果に応じて定期的にモデルがアップグレードされます。**友達を招待して一緒に投票しましょう!**

シナリオに基づいて**新しい言語モデルをトレーニング** する必要がある場合は、[多言語モデル トレーニング プロジェクト](https://github.com/PaddlePaddle/PaddleOCR/discussions/7252) のチュートリアルがデータセットの準備にご利用でき、 プロセス全体を段階的に表示することができます。

元の[多言語 OCR 開発計画](https://github.com/PaddlePaddle/PaddleOCR/issues/1048) には、まだ多くの有用なコーパスと辞書が表示されています

<a name="ビジュアリゼーション"></a>

## 👀 ビジュアリゼーション [more](../doc_en/visualization_en.md)

<details open>
<summary>PP-OCRv3 多言語モデル</summary>
<div align="center">
    <img src="../imgs_results/PP-OCRv3/multi_lang/japan_2.jpg" width="800">
    <img src="../imgs_results/PP-OCRv3/multi_lang/korean_1.jpg" width="800">
</div>
</details>

<details open>
<summary>PP-OCRv3 英語 モデル</summary>
<div align="center">
    <img src="../imgs_results/PP-OCRv3/en/en_1.png" width="800">
    <img src="../imgs_results/PP-OCRv3/en/en_2.png" width="800">
</div>
</details>
<details open>
<summary>PP-OCRv3 中国語 モデル</summary>
<div align="center">
    <img src="../imgs_results/PP-OCRv3/ch/PP-OCRv3-pic001.jpg" width="800">
    <img src="../imgs_results/PP-OCRv3/ch/PP-OCRv3-pic002.jpg" width="800">
    <img src="../imgs_results/PP-OCRv3/ch/PP-OCRv3-pic003.jpg" width="800">
</div>
</details>

<details open>
<summary>PP-Structurev2</summary>
1. レイアウト分析＋テーブル認識
<div align="center">
    <img src="../../ppstructure/docs/table/ppstructure.GIF" width="800">
</div>
2. SER (セマンティックエンティティ認識)
<div align="center">
    <img src="https://user-images.githubusercontent.com/25809855/186094456-01a1dd11-1433-4437-9ab2-6480ac94ec0a.png" width="600">
</div>
<div align="center">
    <img src="https://user-images.githubusercontent.com/14270174/185310636-6ce02f7c-790d-479f-b163-ea97a5a04808.jpg" width="600">
</div>
<div align="center">
    <img src="https://user-images.githubusercontent.com/14270174/185539517-ccf2372a-f026-4a7c-ad28-c741c770f60a.png" width="600">
</div>
3. RE (関係抽出)
<div align="center">
    <img src="https://user-images.githubusercontent.com/25809855/186094813-3a8e16cc-42e5-4982-b9f4-0134dfb5688d.png" width="600">
</div>   
<div align="center">
    <img src="https://user-images.githubusercontent.com/14270174/185393805-c67ff571-cf7e-4217-a4b0-8b396c4f22bb.jpg" width="600">
</div>
<div align="center">
    <img src="https://user-images.githubusercontent.com/14270174/185540080-0431e006-9235-4b6d-b63d-0b3c6e1de48f.jpg" width="600">
</div>
</details>

<a name="ライセンス"></a>

## 📄 ライセンス
このプロジェクトは以下の場所でリリースされています <a href="https://github.com/PaddlePaddle/PaddleOCR/blob/master/LICENSE">Apache 2.0 license</a>
