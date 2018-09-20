---
title: '方法: データ パイプラインでトランスフォーマーを使用する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c39491543c4d3a16202dac3caee50122ba0c7cf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403124"
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>方法: データ パイプラインでトランスフォーマーを使用する

このトピックでには使用する方法を示す基本的な例が含まれています、 [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)データ パイプラインでのクラス。 データ パイプラインを使用してイメージ処理を実行するより詳細な例を参照してください。[チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)です。

*データのパイプライン処理*同時実行プログラミングにおける一般的なパターンです。 データ パイプラインは一連のステージで構成され、各ステージで処理を実行し、その処理の結果を次のステージに渡します。 `transformer` クラスは、入力値を受け取り、その値に対して処理を実行し、別のコンポーネントで使用する結果を生成するため、データ パイプラインにおいて重要なコンポーネントとなっています。

## <a name="example"></a>例

この例では、次のデータ パイプラインを使用して、渡される初期入力値に対して一連の変換を実行します。

1. 最初のステージは、入力の絶対値を計算します。

1. 2 番目のステージは、入力の平方根を計算します。

1. 3 番目のステージは、入力の 2 乗を計算します。

1. 4 番目のステージは、入力の符号を反転します。

1. 5 番目のステージは、最終的な結果をメッセージ バッファーに書き込みます。

最後に、この例はパイプラインの結果をコンソールに出力します。

[!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
The result is -42.
```

一般に、データ パイプラインのステージは、入力値と異なる種類の値を出力します。 この例では、2 番目のステージは入力として `int` 型の値を取得し、出力としてその値の平方根 (`double` 型) を生成します。

> [!NOTE]
>  この例のデータ パイプラインは、例示のみを目的としています。 各変換操作での処理量が少ないため、メッセージ パッシングを実行するのに必要なオーバーヘッドがデータ パイプラインを使用するメリットを上回る場合があります。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`data-pipeline.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc data-pipeline.cpp**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)

