---
title: 描画コード (ATL チュートリアル、パート 4) の変更 |Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fed83cd67ff596581440fa317355186653a0cbec
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760426"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>描画コードの変更 (ATL チュートリアル、パート 4)

既定では、コントロールの描画コードを表示正方形やテキスト**PolyCtl**します。 この手順で、さらに興味深いを表示するコードを変更します。 次のタスクが含まれます。

- ヘッダー ファイルの変更

- 変更、`OnDraw`関数

- 多角形の点を計算するメソッドを追加します。

- 塗りつぶしの色を初期化しています

## <a name="modifying-the-header-file"></a>ヘッダー ファイルの変更

数値演算関数のサポートを追加することで開始`sin`と`cos`、どちらを使用する多角形の点を計算し、格納する配列を作成して配置します。

#### <a name="to-modify-the-header-file"></a>ヘッダー ファイルを変更するには

1. 行を追加`#include <math.h>`PolyCtl.h の先頭にします。 このよう、ファイルの先頭になります。

     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

2. 多角形の頂点の計算と型の配列に格納されます`POINT`、そのための定義の後に、配列を追加`m_nSides`PolyCtl.h で。

     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>OnDraw メソッドを変更します。

変更する必要がありますので、 `OnDraw` PolyCtl.h メソッド。 追加のコードが新しいペンと、多角形を描画するために使用するブラシを作成しを呼び出して、`Ellipse`と`Polygon`実際の描画を実行する Win32 API 関数。

#### <a name="to-modify-the-ondraw-function"></a>OnDraw 関数を変更するには

1. 既存`OnDraw`PolyCtl.h でメソッドを次のコード。

     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>多角形の点を計算するメソッドを追加します。

というメソッドを追加`CalcPoints`、多角形の境界を形成する点の座標を計算します。 これらの計算は、関数に渡される RECT 変数に基づいて構築します。

#### <a name="to-add-the-calcpoints-method"></a>CalcPoints メソッドを追加するには

1. 宣言を追加`CalcPoints`を`IPolyCtl`のパブリック セクション、 `CPolyCtl` PolyCtl.h でクラス。

     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

     パブリック セクションの最後の部分、`CPolyCtl`クラスのようになります。

     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

2. この実装を追加、 `CalcPoints` PolyCtl.cpp の末尾に関数。

     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>塗りつぶしの色を初期化しています

初期化`m_clrFillColor`既定色を使用します。

#### <a name="to-initialize-the-fill-color"></a>塗りつぶしの色を初期化するには

1. この行を追加することで、既定の色として緑を使用して、 `CPolyCtl` PolyCtl.h でコンス トラクター。

     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

コンス トラクターは、次のようになります。

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト

コントロールを再構築します。 引き続き開くことがある場合、PolyCtl.htm ファイルが閉じられるかどうかを確認し、**多角形のビルド**上、**ビルド**メニュー。 PolyCtl.htm ページで、もう一度からコントロールを表示することが、今度は、ActiveX コントロール テスト コンテナーを使用します。

#### <a name="to-use-the-activex-control-test-container"></a>ActiveX コントロール テスト コンテナーを使用するには

1. ビルドし、ActiveX コントロール テスト コンテナーを開始します。 詳細については、次を参照してください。 [TSTCON サンプル: ActiveX コントロール テスト コンテナー](../visual-cpp-samples.md)します。

2. テスト コンテナーで、上、**編集** メニューのをクリックして**新しいコントロールを挿入**します。

3. 呼び出されますコントロールを検索`PolyCtl Class`、 をクリック**OK**します。 円の中の緑の三角形が表示されます。

次の手順を実行して辺の数を変更してください。 テスト コンテナー内からデュアル インターフェイスのプロパティを変更するには使用**メソッドの呼び出し**します。

#### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>テスト コンテナーからコントロールのプロパティを変更するには

1. テスト コンテナーで、次のようにクリックします。**メソッドの呼び出し**上、**コントロール**メニュー。

     **メソッドの呼び出し** ダイアログ ボックスが表示されます。

2. 選択、 **PropPut**のバージョン、**辺**プロパティから、**メソッド名**ドロップダウン リスト ボックス。

3. 型`5`で、**パラメーター値**ボックスで、[**値の設定**、] をクリック**Invoke**します。

コントロールが変更されないことに注意してください。 辺の数を内部的に設定して変更したにもかかわらず、`m_nSides`変数、これが発生しなかったコントロールに再描画します。 別のアプリケーションに切り替えるし、テスト コンテナーに切り替えての場合は、コントロールが再描画し、正しい辺の数が表示されます。

この問題を修正するには、呼び出しを追加、`FireViewChange`で定義された関数`IViewObjectExImpl`辺の数を設定した後、します。 コントロールが、独自のウィンドウで実行されている場合`FireViewChange`が呼び出す、`InvalidateRect`メソッドを直接します。 コントロールが、ウィンドウなしで実行されている場合、`InvalidateRect`コンテナーのサイトのインターフェイスでメソッドが呼び出されます。 これは強制的に再描画コントロールです。

#### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange への呼び出しを追加するには

1. 呼び出しを追加して PolyCtl.cpp を更新`FireViewChange`を`put_Sides`メソッド。 完了したら、`put_Sides`メソッドは、次のようになります。

     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

追加した後`FireViewChange`、再構築したり、コントロールの ActiveX コントロール テスト コンテナーにもう一度お試しください。 この時点の辺の数を変更し、をクリックして`Invoke`コントロールのすぐに変更を表示する必要があります。

次の手順では、イベントを追加します。

[手順 3 に戻る](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [手順 5 に](../atl/adding-an-event-atl-tutorial-part-5.md)

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)   
[テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)

