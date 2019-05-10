---
title: 'チュートリアル: イメージ処理ネットワークの作成'
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: ff5e0bcae3d23dc914d93a062ec36ea1435ce1b2
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856302"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>チュートリアル: イメージ処理ネットワークの作成

このドキュメントでは、イメージ処理を実行する非同期メッセージ ブロックのネットワークを作成する方法を示します。

ネットワークでは、その特性に基づいてイメージを実行する操作を決定します。 この例では、*データフロー*モデルをネットワーク経由のルートのイメージ。 このデータフロー モデルでは、プログラム内の独立したコンポーネント同士が、メッセージを送信することによって相互に通信します。 コンポーネントは、メッセージを受信したときに何らかのアクションを実行し、そのアクションの結果を別のコンポーネントに渡すできます。 これを比較、*制御フロー*モデルでは、アプリケーションを使用する制御構造、たとえば、条件付きステートメント、ループ、およびでは、プログラムで操作の順序を制御します。

データ フローに基づくネットワークを作成、*パイプライン*のタスク。 パイプラインの各ステージでは、タスク全体の一部が同時に実行します。 これは、自動車製造の組み立てラインに例えることができます。 各車両が組み立てラインを通過フレームを 1 つのステーションにアセンブル、エンジン、およびなど別がインストールされます。 組み立てラインを同時にアセンブルする複数の車両を有効にするには、一度に車両全体を組み立てるよりスループットを向上を提供します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [方法: メッセージ ブロック フィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [チュートリアル: データフロー エージェントの作成](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

また、このチュートリアルを開始する前に、GDI + の基本を理解することをお勧めします。

##  <a name="top"></a> セクション

このチュートリアルは、次のセクションで構成されています。

- [イメージ処理機能を定義します。](#functionality)

- [イメージ処理ネットワークを作成します。](#network)

- [コード例全体](#complete)

##  <a name="functionality"></a> イメージ処理機能を定義します。

このセクションでは、ディスクから読み取られるイメージを使用する、イメージ処理ネットワークを使用するサポート機能が表示されます。

次の関数では、`GetRGB`と`MakeColor`の抽出、およびそれぞれに特定の色の個々 のコンポーネントを結合します。

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

次の関数では、`ProcessImage`を呼び出し、指定された[std::function](../../standard-library/function-class.md) GDI + での各ピクセルの色の値を変換するオブジェクト[ビットマップ](/windows/desktop/api/gdiplusheaders/nl-gdiplusheaders-bitmap)オブジェクト。 `ProcessImage`関数は、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムを並列にビットマップの各行を処理します。

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

次の関数では、 `Grayscale`、 `Sepiatone`、`ColorMask`と`Darken`を呼び出し、`ProcessImage`内の各ピクセルの色の値を変換する関数を`Bitmap`オブジェクト。 これらの各関数は、ラムダ式を使用して、1 ピクセルの色変換を定義します。

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

次の関数では、`GetColorDominance`も呼び出して、`ProcessImage`関数。 ただし、それぞれの色の値を変更するには、代わりにこの関数は[concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)赤、緑、または青の色コンポーネントの大部分のイメージであるかどうかを計算するオブジェクト。

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

次の関数では、`GetEncoderClsid`エンコーダーの指定された MIME 型のクラス識別子を取得します。 アプリケーションでは、この関数を使用して、ビットマップのエンコーダーを取得します。

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[トップ](#top)]

##  <a name="network"></a> イメージ処理ネットワークを作成します。

このセクションでは、指定されたディレクトリにすべての JPEG (.jpg) イメージでイメージ処理を実行する非同期メッセージ ブロックのネットワークを作成する方法について説明します。 ネットワークでは、次の画像処理操作を実行します。

1. Tom は、作成したすべてのイメージをグレースケールに変換します。

1. ドミナント カラーに赤のある任意のイメージの緑、青のコンポーネントを削除し、それを暗きます。

1. その他の画像を抑えます。 セピアが適用されます。

ネットワークには、これらの条件のいずれかに一致する最初の画像処理操作のみが適用されます。 たとえば、イメージは、Tom によってが作成されが赤の主調色として場合、イメージはグレースケール変換のみ。

ネットワークが各イメージ処理操作を実行した後、イメージ ディスクとして保存ビットマップ (.bmp) ファイル。

次の手順では、このイメージ処理ネットワークを実装し、そのネットワークを指定したディレクトリ内の各 JPEG 画像に適用する関数を作成する方法を示します。

#### <a name="to-create-the-image-processing-network"></a>イメージ処理ネットワークを作成するには

1. 関数を作成`ProcessImages`ディスク上のディレクトリの名前を受け取る。

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. `ProcessImages`関数を作成、`countdown_event`変数。 `countdown_event`クラスがこのチュートリアルの後半で示すようにします。

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. 作成、 [std::map](../../standard-library/map-class.md)オブジェクトを関連付ける、`Bitmap`元のファイル名を持つオブジェクト。

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. イメージ処理ネットワークのメンバーを定義する次のコードを追加します。

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. 次のコードをネットワーク接続を追加します。

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. ディレクトリに、ネットワークの先頭に各 JPEG ファイルの完全なパスを送信する次のコードを追加します。

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. 待つ、 `countdown_event` 0 になる変数です。

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

ネットワークのメンバーを次の表に示します。

|メンバー|説明|
|------------|-----------------|
|`load_bitmap`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)を読み込むオブジェクトを`Bitmap`ディスクからオブジェクトし、にエントリを追加、`map`にイメージを元のファイル名に関連付けるオブジェクト。|
|`loaded_bitmaps`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)画像処理のフィルターに読み込まれるイメージを送信するオブジェクト。|
|`grayscale`|A`transformer`グレースケール Tom によって作成されたイメージに変換するオブジェクト。 その著者を決定するのにイメージのメタデータを使用します。|
|`colormask`|A`transformer`主調色として赤が設定されたイメージから、緑、青の色のコンポーネントを削除するオブジェクト。|
|`darken`|A`transformer`主調色として赤が設定されたイメージを暗くオブジェクト。|
|`sepiatone`|A `transformer` Tom によって作成されていませんが、主に赤ではないイメージをセピア トーンを適用するオブジェクト。|
|`save_bitmap`|A`transformer`保存、処理するオブジェクト`image`ビットマップとしてディスクにします。 `save_bitmap` 元のファイル名を取得、`map`オブジェクト、および .bmp をファイル名拡張子を変更します。|
|`delete_bitmap`|A`transformer`イメージ用のメモリを解放するオブジェクト。|
|`decrement`|A [concurrency::call](../../parallel/concrt/reference/call-class.md)ネットワーク内のターミナル ノードとして機能するオブジェクト。 これをデクリメント、`countdown_event`オブジェクトからイメージが処理されたことをメイン アプリケーションに通知します。|

`loaded_bitmaps`メッセージ バッファーが重要ですので、として、`unbounded_buffer`オブジェクトを提供`Bitmap`複数の受信者からオブジェクト。 ターゲット ブロックが許可される場合、`Bitmap`オブジェクト、`unbounded_buffer`オブジェクトによって提供されていない`Bitmap`は他のターゲット オブジェクト。 そのためにオブジェクトをリンクする順序、`unbounded_buffer`オブジェクトが重要です。 `grayscale`、 `colormask`、および`sepiatone`メッセージの各ブロックを受け入れるようにフィルターを使用してのみ特定`Bitmap`オブジェクト。 `decrement`メッセージ バッファーが、重要なターゲットの`loaded_bitmaps`すべてを受け入れるために、メッセージ バッファー`Bitmap`他のメッセージ バッファーによって拒否されたオブジェクト。 `unbounded_buffer`の順序でメッセージを伝達するオブジェクトが必要です。 そのため、`unbounded_buffer`オブジェクトは、新しいターゲット ブロックにリンクされてし、現在のターゲット ブロックがメッセージを受け入れるない場合は、メッセージを受け入れるまでをブロックします。

アプリケーションでは、その複数のメッセージ ブロックの最初にメッセージを受け取り、1 つのメッセージ ブロックだけではなく、メッセージの処理が必要な場合、別のメッセージ ブロックの型をなど、使用できる`overwrite_buffer`します。 `overwrite_buffer`クラスは、一度に 1 つのメッセージを保持するが、各ターゲットには、そのメッセージを伝達します。

次の図は、イメージ処理ネットワークを示しています。

![イメージ処理ネットワーク](../../parallel/concrt/media/concrt_imageproc.png "イメージ処理ネットワーク")

`countdown_event`この例ではオブジェクトがすべてのイメージが処理されたときに、メイン アプリケーションを通知するために、イメージ処理ネットワークを使用できます。 `countdown_event`クラスで使用する[concurrency::event](../../parallel/concrt/reference/event-class.md)オブジェクトからカウンターの値が 0 に達したときに通知します。 メインのアプリケーションは、it がネットワークにファイル名を送信するたびにカウンターをインクリメントします。 ネットワーク デクリメントのターミナル ノードには、カウンターの各イメージの処理が完了します。 メインのアプリケーションでは、指定されたディレクトリを走査後の待機、`countdown_event`オブジェクトからそのカウンターをゼロに達したことを通知します。

次の例は、`countdown_event`クラス。

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[トップ](#top)]

##  <a name="complete"></a> 完全な例

コード例全体を次に示します。 `wmain`関数は、GDI + ライブラリと呼び出しを管理、 `ProcessImages` 、JPEG を処理する関数にファイルを`Sample Pictures`ディレクトリ。

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

次の図は、サンプル出力を示します。 各ソース イメージは、その対応する変更後のイメージの上です。

![サンプル出力の例では、](../../parallel/concrt/media/concrt_imageout.png "サンプル出力の例では、")

`Lighthouse` Tom Alphin によってが作成され、そのため、グレースケールに変換されます。 `Chrysanthemum`、 `Desert`、 `Koala`、および`Tulips`主調色として red があるためと青と緑のカラー コンポーネントを削除しているし、暗くなります。 `Hydrangeas`、 `Jellyfish`、および`Penguins`既定条件に一致しているため toned セピアは。

[[トップ](#top)]

### <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`image-processing-network.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe /DUNICODE /EHsc image-processing-network.cpp /link gdiplus.lib**

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
