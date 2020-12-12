---
description: '詳細については、「チュートリアル: Image-Processing ネットワークを作成する」を参照してください。'
title: 'チュートリアル: イメージ処理ネットワークの作成'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 1cdd94d6cad6ee76c02b7eb2cf8b4ca38a53fa96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169308"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>チュートリアル: イメージ処理ネットワークの作成

このドキュメントでは、イメージ処理を実行する非同期メッセージブロックのネットワークを作成する方法について説明します。

ネットワークでは、その特性に基づいてイメージに対して実行する操作を決定します。 この例では、データ *フロー* モデルを使用して、ネットワーク経由でイメージをルーティングします。 このデータフロー モデルでは、プログラム内の独立したコンポーネント同士が、メッセージを送信することによって相互に通信します。 コンポーネントは、メッセージを受信すると、何らかのアクションを実行し、そのアクションの結果を別のコンポーネントに渡すことができます。 これを *制御フロー* モデルと比較します。このモデルでは、アプリケーションが制御構造 (たとえば、条件付きステートメントやループなど) を使用して、プログラムの操作の順序を制御します。

データフローに基づくネットワークによって、タスクの *パイプライン* が作成されます。 パイプラインの各ステージは、タスク全体の一部を同時に実行します。 これは、自動車製造の組み立てラインに例えることができます。 各車両が組み立てラインを通過すると、1つのステーションがフレームをアセンブルし、別のステーションがエンジンをインストールします。 複数の車両を同時に組み立てられるようにすることで、アセンブリラインは、一度に1つの完全な車両をアセンブルするよりも高いスループットを実現します。

## <a name="prerequisites"></a>前提条件

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [方法: メッセージブロックフィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [チュートリアル: データフローエージェントの作成](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

また、このチュートリアルを開始する前に、GDI + の基本を理解しておくことをお勧めします。

## <a name="sections"></a><a name="top"></a> 各項

このチュートリアルは、次のセクションで構成されています。

- [イメージ処理機能の定義](#functionality)

- [イメージ処理ネットワークの作成](#network)

- [完全な例](#complete)

## <a name="defining-image-processing-functionality"></a><a name="functionality"></a> イメージ処理機能の定義

このセクションでは、イメージ処理ネットワークがディスクから読み取られたイメージを操作するために使用するサポート機能について説明します。

次の関数とは、 `GetRGB` `MakeColor` それぞれ、特定の色の個々のコンポーネントを抽出して結合します。

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

次の関数は、 `ProcessImage` 指定された [std:: function](../../standard-library/function-class.md) オブジェクトを呼び出して、gdi + [ビットマップ](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) オブジェクトの各ピクセルの色の値を変換します。 関数は、 `ProcessImage` [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムを使用して、ビットマップの各行を並行して処理します。

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

次の関数、、、、およびは、関数を呼び出して、 `Grayscale` `Sepiatone` オブジェクトの `ColorMask` `Darken` `ProcessImage` 各ピクセルの色の値を変換し `Bitmap` ます。 これらの各関数は、ラムダ式を使用して、1つのピクセルのカラー変換を定義します。

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

次の関数は、 `GetColorDominance` 関数も呼び出し `ProcessImage` ます。 ただし、この関数は、各色の値を変更するのではなく、 [concurrency:: 組み合わせ](../../parallel/concrt/reference/combinable-class.md) 可能オブジェクトを使用して、赤、緑、または青のカラーコンポーネントがイメージを優先するかどうかを計算します。

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

次の関数は、 `GetEncoderClsid` エンコーダーの指定された MIME の種類のクラス識別子を取得します。 アプリケーションでは、ビットマップのエンコーダーを取得するために、この関数を使用します。

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[上](#top)]

## <a name="creating-the-image-processing-network"></a><a name="network"></a> イメージ処理ネットワークの作成

このセクションでは、特定のディレクトリ内のすべての JPEG (.jpg) イメージでイメージ処理を実行する非同期メッセージブロックのネットワークを作成する方法について説明します。 ネットワークは、次の画像処理操作を実行します。

1. Tom によって作成されたイメージの場合は、グレースケールに変換します。

1. 最も優先色が赤のイメージの場合は、緑と青のコンポーネントを削除してから暗くします。

1. その他のイメージの場合は、セピア調を適用します。

ネットワークでは、これらの条件のいずれかに一致する最初のイメージ処理操作のみが適用されます。 たとえば、画像が Tom によって作成され、その主要色が赤の場合、イメージはグレースケールにのみ変換されます。

ネットワークは、各イメージ処理操作を実行した後、イメージをビットマップ (.bmp) ファイルとしてディスクに保存します。

次の手順では、このイメージ処理ネットワークを実装する関数を作成し、そのネットワークを特定のディレクトリ内のすべての JPEG イメージに適用する方法を示します。

#### <a name="to-create-the-image-processing-network"></a>イメージ処理ネットワークを作成するには

1. `ProcessImages`ディスク上のディレクトリの名前を取得する関数を作成します。

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. 関数で、 `ProcessImages` 変数を作成 `countdown_event` します。 `countdown_event`クラスは、このチュートリアルで後ほど説明します。

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. オブジェクトを元のファイル名に関連付ける [std:: map](../../standard-library/map-class.md) オブジェクトを作成し `Bitmap` ます。

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. 次のコードを追加して、イメージ処理ネットワークのメンバーを定義します。

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. ネットワークに接続するための次のコードを追加します。

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. 次のコードを追加して、ディレクトリ内の各 JPEG ファイルの完全なパスをネットワークの先頭に送信します。

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. 変数が0になるまで待ち `countdown_event` ます。

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

ネットワークのメンバーを次の表に示します。

|メンバー|説明|
|------------|-----------------|
|`load_bitmap`|オブジェクト[](../../parallel/concrt/reference/transformer-class.md)を `Bitmap` ディスクから読み込み、オブジェクトにエントリを追加して、イメージを元の `map` ファイル名に関連付ける concurrency:: トランスフォーマーオブジェクト。|
|`loaded_bitmaps`|イメージ処理フィルターに読み込まれたイメージを送信する [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) オブジェクト。|
|`grayscale`|`transformer`Tom によって作成されたイメージをグレースケールに変換するオブジェクト。 イメージのメタデータを使用して、その作成者を決定します。|
|`colormask`|`transformer`赤が最も高い色のイメージから緑と青のカラーコンポーネントを削除するオブジェクト。|
|`darken`|赤のイメージを最も重要な `transformer` 色として暗くするオブジェクト。|
|`sepiatone`|`transformer`Tom によって作成されておらず、主に赤色ではない画像にセピア色を適用するオブジェクト。|
|`save_bitmap`|`transformer`処理されたを `image` ディスクにビットマップとして保存するオブジェクト。 `save_bitmap` オブジェクトから元のファイル名を取得 `map` し、そのファイル名拡張子を .bmp に変更します。|
|`delete_bitmap`|`transformer`イメージのメモリを解放するオブジェクト。|
|`decrement`|ネットワークのターミナルノードとして機能する [concurrency:: call](../../parallel/concrt/reference/call-class.md) オブジェクト。 オブジェクトをデクリメントして、 `countdown_event` イメージが処理されたことをメインアプリケーションに通知します。|

`loaded_bitmaps`メッセージバッファーは、オブジェクトとして `unbounded_buffer` 複数の受信側にオブジェクトを提供するため、重要です `Bitmap` 。 ターゲットブロックがオブジェクトを受け入れると、オブジェクトはそのオブジェクトを `Bitmap` `unbounded_buffer` `Bitmap` 他のターゲットに提供しません。 したがって、オブジェクトをオブジェクトにリンクする順序は `unbounded_buffer` 重要です。 `grayscale`、 `colormask` 、およびの `sepiatone` 各メッセージブロックは、特定のオブジェクトのみを受け入れるフィルターを使用し `Bitmap` ます。 メッセージバッファー `decrement` は、 `loaded_bitmaps` `Bitmap` 他のメッセージバッファーによって拒否されたすべてのオブジェクトを受け入れるため、メッセージバッファーの重要なターゲットとなります。 `unbounded_buffer`メッセージを順番に伝達するには、オブジェクトが必要です。 したがって、 `unbounded_buffer` オブジェクトは、新しいターゲットブロックがリンクされるまでブロックし、現在のターゲットブロックがメッセージを受け入れない場合はメッセージを受け入れます。

アプリケーションで、メッセージを最初に受け取るメッセージブロックだけではなく、メッセージを処理する必要がある場合は、などの別のメッセージブロックの型を使用でき `overwrite_buffer` ます。 クラスは、一度 `overwrite_buffer` に1つのメッセージを保持しますが、そのメッセージを各ターゲットに伝達します。

次の図は、イメージ処理ネットワークを示しています。

![画像処理ネットワーク](../../parallel/concrt/media/concrt_imageproc.png "画像処理ネットワーク")

`countdown_event`この例のオブジェクトを使用すると、イメージ処理ネットワークは、すべてのイメージが処理されたことをメインアプリケーションに通知できます。 クラスは、 `countdown_event` カウンター値がゼロに達したときに、 [concurrency:: event](../../parallel/concrt/reference/event-class.md) オブジェクトを使用して通知します。 メインアプリケーションは、ファイル名をネットワークに送信するたびにカウンターをインクリメントします。 ネットワークのターミナルノードは、各イメージが処理された後にカウンターをデクリメントします。 メインアプリケーションは、指定されたディレクトリを走査した後、その `countdown_event` カウンターが0に達したことをオブジェクトが通知するまで待機します。

クラスの例を次に示し `countdown_event` ます。

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[上](#top)]

## <a name="the-complete-example"></a><a name="complete"></a> 完全な例

コード例全体を次に示します。 `wmain`関数は GDI + ライブラリを管理し、関数を呼び出して、 `ProcessImages` ディレクトリ内の JPEG ファイルを処理し `Sample Pictures` ます。

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

次の図は、サンプル出力を示しています。 各ソースイメージは、対応する変更されたイメージの上にあります。

![例のサンプル出力](../../parallel/concrt/media/concrt_imageout.png "例のサンプル出力")

`Lighthouse` は Tom Alphin によって作成されるため、グレースケールに変換されます。 `Chrysanthemum`、、、およびは、最も重要 `Desert` `Koala` `Tulips` な色として赤を持ちます。したがって、青と緑のカラーコンポーネントが削除され、暗くなります。 `Hydrangeas`、 `Jellyfish` 、および `Penguins` は既定の基準に一致するため、セピア toned です。

[[上](#top)]

### <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `image-processing-network.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

**/DUNICODE/EHsc image-processing-network をcl.exe します。**

## <a name="see-also"></a>関連項目

[同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
