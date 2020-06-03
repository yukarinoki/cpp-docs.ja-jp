---
title: 描画コードの変更 (ATL チュートリアル、パート 4)
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 319a27b55c394349de751546457b0741c0799cfc
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167644"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>描画コードの変更 (ATL チュートリアル、パート 4)

既定では、コントロールの描画コードに四角形とテキスト**polyctl.htm**が表示されます。 この手順では、さらに興味深いものを表示するようにコードを変更します。 次のタスクが関係します。

- ヘッダーファイルの変更

- 関数の`OnDraw`変更

- 多角形のポイントを計算するメソッドの追加

- 塗りつぶしの色を初期化しています

## <a name="modifying-the-header-file"></a>ヘッダーファイルの変更

まず、算術関数`sin`と`cos`のサポートを追加します。これは、多角形のポイントの計算と、位置を格納する配列の作成に使用されます。

### <a name="to-modify-the-header-file"></a>ヘッダーファイルを変更するには

1. Polyctl.htm の先頭`#include <math.h>`に行を追加します。 ファイルの先頭は次のようになります。

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. `IProvideClassInfo`インターフェイスを実装して、次のコードを polyctl.htm に追加して、コントロールのメソッド情報を提供します。 `CPolyCtl`クラスで、次の行を置き換えます。

    ```cpp
    public CComControl<CPolyCtl>
    ```

    with

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    とで`BEGIN_COM_MAP(CPolyCtl)`、次の行を追加します。

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. 多角形のポイントが計算されると、型`POINT`の配列に格納されます。そのため、polyctl.htm の definition ステートメント`short m_nSides;`の後に配列を追加します。

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>OnDraw メソッドの変更

ここで、Polyctl.htm の`OnDraw`メソッドを変更する必要があります。 追加するコードでは、多角形を描画するために使用する新しいペンとブラシを作成します`Ellipse` 。 `Polygon`次に、関数と Win32 API 関数を呼び出して、実際の描画を実行します。

### <a name="to-modify-the-ondraw-function"></a>OnDraw 関数を変更するには

1. Polyctl.htm の既存`OnDraw`のメソッドを次のコードに置き換えます。

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>多角形のポイントを計算するメソッドの追加

という`CalcPoints`メソッドを追加します。これにより、多角形の境界を構成する点の座標が計算されます。 これらの計算は、関数に渡される RECT 変数に基づいて行われます。

### <a name="to-add-the-calcpoints-method"></a>CalcPoints メソッドを追加するには

1. Polyctl.htm の`CPolyCtl`クラスの`CalcPoints` `IPolyCtl`パブリックセクションに、の宣言を追加します。

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    `CPolyCtl`クラスのパブリックセクションの最後の部分は次のようになります。

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. 次の`CalcPoints`関数の実装を polyctl.htm の末尾に追加します。

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>塗りつぶしの色を初期化しています

既定`m_clrFillColor`の色で初期化します。

### <a name="to-initialize-the-fill-color"></a>塗りつぶしの色を初期化するには

1. Polyctl.htm の`CPolyCtl`コンストラクターに次の行を追加して、既定の色として緑色を使用します。

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

コンストラクターは次のようになります。

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト

コントロールをリビルドします。 Polyctl.htm ファイルが開いている場合は閉じていることを確認し、[**ビルド**] メニューの [**多角形のビルド**] をクリックします。 Polyctl.htm ページからもう一度コントロールを表示できますが、今度は ActiveX コントロールテストコンテナーを使用します。

### <a name="to-use-the-activex-control-test-container"></a>ActiveX コントロールテストコンテナーを使用するには

1. ActiveX コントロールテストコンテナーをビルドして開始します。 [TSTCON サンプル: ActiveX コントロールテストコンテナー](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon)は GitHub にあります。

    > [!NOTE]
    > に`ATL::CW2AEX`関連するエラーの場合は、スクリプト .cpp で`TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` 、 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );`行をに`TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );`置き換え`TRACE( "Source Text: %s\n", bstrSourceLineText );`、行をに置き換えます。<br/>
    > に関連`HMONITOR`するエラーが発生した`TCProps`場合は、プロジェクトで stdafx.h を開き、次のように置き換えます。
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    >
    > with
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. **テストコンテナー**で、[**編集**] メニューの [**新しいコントロールの挿入**] をクリックします。

1. という名前`PolyCtl class`のコントロールを見つけて、[ **OK]** をクリックします。 丸の中に緑色の三角形が表示されます。

次の手順に従って、辺の数を変更してみてください。 **テストコンテナー**内からデュアルインターフェイスのプロパティを変更するには、 **Invoke メソッド**を使用します。

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>テストコンテナー内からコントロールのプロパティを変更するには

1. [**テストコンテナー**] で、[**コントロール**] メニューの [**メソッドの呼び出し**] をクリックします。

    [**メソッドの呼び出し**] ダイアログボックスが表示されます。

1. [**メソッド名**] ボックスの一覧から、[ **PropPut** version of the**両辺**] プロパティを選択します。

1. [ `5` **パラメーター値**] ボックスに「」と入力し、[**値の設定**] をクリックして、[**呼び出し**] をクリックします。

コントロールは変更されないことに注意してください。 `m_nSides`変数を設定することによって内部の辺の数を変更しても、コントロールは再描画されませんでした。 別のアプリケーションに切り替えてから**テストコンテナー**に戻すと、コントロールが再描画され、正しい数の辺があることがわかります。

この問題を修正するには、辺の`FireViewChange`数を設定し`IViewObjectExImpl`た後にで定義された関数の呼び出しを追加します。 コントロールが独自のウィンドウで実行されて`FireViewChange`いる場合、 `InvalidateRect`はメソッドを直接呼び出します。 コントロールがウィンドウなしで実行され`InvalidateRect`ている場合、メソッドはコンテナーのサイトインターフェイスで呼び出されます。 これにより、コントロール自体が強制的に再描画されます。

### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange への呼び出しを追加するには

1. メソッドにの呼び出しを追加して、 `FireViewChange` polyctl.htm を更新します。 `put_Sides` 完了すると、メソッドは`put_Sides`次のようになります。

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

追加`FireViewChange`した後、ActiveX コントロールテストコンテナーでもう一度コントロールをリビルドして、もう一度試してみてください。 今度は、辺の数を変更し、を`Invoke`クリックすると、コントロールの変更がすぐに表示されます。

次の手順では、イベントを追加します。

手順[3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) . に戻り[、手順5に](../atl/adding-an-event-atl-tutorial-part-5.md)&#124; ます。

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)<br/>
[テストコンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)
