---
description: '詳細情報: 描画コードの変更 (ATL チュートリアル、パート 4)'
title: 描画コードの変更 (ATL チュートリアル、パート 4)
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 4d134930bf2c9bc886a3c59a68db5a52f7c6ca7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153383"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>描画コードの変更 (ATL チュートリアル、パート 4)

既定では、コントロールの描画コードに四角形とテキスト **polyctl.htm** が表示されます。 この手順では、さらに興味深いものを表示するようにコードを変更します。 次のタスクが関係します。

- ヘッダーファイルの変更

- 関数の変更 `OnDraw`

- 多角形のポイントを計算するメソッドの追加

- 塗りつぶしの色を初期化しています

## <a name="modifying-the-header-file"></a>ヘッダーファイルの変更

まず、算術関数とのサポートを追加します `sin` `cos` 。これは、多角形のポイントの計算と、位置を格納する配列の作成に使用されます。

### <a name="to-modify-the-header-file"></a>ヘッダーファイルを変更するには

1. `#include <math.h>`Polyctl.htm の先頭に行を追加します。 ファイルの先頭は次のようになります。

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. インターフェイスを実装し `IProvideClassInfo` て、次のコードを polyctl.htm に追加して、コントロールのメソッド情報を提供します。 クラスで `CPolyCtl` 、次の行を置き換えます。

    ```cpp
    public CComControl<CPolyCtl>
    ```

    with

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    とで `BEGIN_COM_MAP(CPolyCtl)` 、次の行を追加します。

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. 多角形のポイントが計算されると、型の配列に格納されます `POINT` 。そのため、polyctl.htm の definition ステートメントの後に配列を追加します `short m_nSides;` 。

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>OnDraw メソッドの変更

ここで、Polyctl.htm のメソッドを変更する必要があり `OnDraw` ます。 追加するコードでは、多角形を描画するために使用する新しいペンとブラシを作成します。次に、 `Ellipse` 関数と Win32 API 関数を呼び出して、 `Polygon` 実際の描画を実行します。

### <a name="to-modify-the-ondraw-function"></a>OnDraw 関数を変更するには

1. `OnDraw`Polyctl.htm の既存のメソッドを次のコードに置き換えます。

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>多角形のポイントを計算するメソッドの追加

というメソッドを追加し `CalcPoints` ます。これにより、多角形の境界を構成する点の座標が計算されます。 これらの計算は、関数に渡される RECT 変数に基づいて行われます。

### <a name="to-add-the-calcpoints-method"></a>CalcPoints メソッドを追加するには

1. `CalcPoints` `IPolyCtl` Polyctl.htm のクラスのパブリックセクションに、の宣言を追加し `CPolyCtl` ます。

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    クラスのパブリックセクションの最後の部分は次の `CPolyCtl` ようになります。

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. 次の関数の実装 `CalcPoints` を polyctl.htm の末尾に追加します。

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>塗りつぶしの色を初期化しています

`m_clrFillColor`既定の色で初期化します。

### <a name="to-initialize-the-fill-color"></a>塗りつぶしの色を初期化するには

1. Polyctl.htm のコンストラクターに次の行を追加して、既定の色として緑色を使用し `CPolyCtl` ます。

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

コンストラクターは次のようになります。

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>コントロールのビルドとテスト

コントロールをリビルドします。 PolyCtl.htm ファイルが開いている場合は閉じていることを確認し、[**ビルド**] メニューの [**多角形のビルド**] をクリックします。 [PolyCtl.htm] ページからもう一度コントロールを表示できますが、今度は ActiveX コントロールテストコンテナーを使用します。

### <a name="to-use-the-activex-control-test-container"></a>ActiveX コントロールテストコンテナーを使用するには

1. ActiveX コントロールテストコンテナーをビルドして開始します。 [TSTCON サンプル: ActiveX コントロールテストコンテナー](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon)は GitHub にあります。

    > [!NOTE]
    > に関連するエラーの場合は、 `ATL::CW2AEX` スクリプト .cpp で、行をに置き換え、 `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` 行をに置き換え `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );` `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` `TRACE( "Source Text: %s\n", bstrSourceLineText );` ます。<br/>
    > に関連するエラーが発生した場合は `HMONITOR` 、プロジェクトで stdafx.h を開き、 `TCProps` 次のように置き換えます。
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

1. **テストコンテナー** で、[**編集**] メニューの [**新しいコントロールの挿入**] をクリックします。

1. という名前のコントロールを見つけ `PolyCtl class` て、[ **OK]** をクリックします。 丸の中に緑色の三角形が表示されます。

次の手順に従って、辺の数を変更してみてください。 **テストコンテナー** 内からデュアルインターフェイスのプロパティを変更するには、 **Invoke メソッド** を使用します。

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>テストコンテナー内からコントロールのプロパティを変更するには

1. [**テストコンテナー**] で、[**コントロール**] メニューの [**メソッドの呼び出し**] をクリックします。

    [ **メソッドの呼び出し** ] ダイアログボックスが表示されます。

1. [**メソッド名**] ボックスの一覧から、[ **PropPut** version of the **両辺**] プロパティを選択します。

1. [ `5` **パラメーター値** ] ボックスに「」と入力し、[ **値の設定**] をクリックして、[ **呼び出し**] をクリックします。

コントロールは変更されないことに注意してください。 変数を設定することによって内部の辺の数を変更しても `m_nSides` 、コントロールは再描画されませんでした。 別のアプリケーションに切り替えてから **テストコンテナー** に戻すと、コントロールが再描画され、正しい数の辺があることがわかります。

この問題を修正するには、 `FireViewChange` `IViewObjectExImpl` 辺の数を設定した後にで定義された関数の呼び出しを追加します。 コントロールが独自のウィンドウで実行されている場合、 `FireViewChange` は `InvalidateRect` メソッドを直接呼び出します。 コントロールがウィンドウなしで実行されている場合、 `InvalidateRect` メソッドはコンテナーのサイトインターフェイスで呼び出されます。 これにより、コントロール自体が強制的に再描画されます。

### <a name="to-add-a-call-to-fireviewchange"></a>FireViewChange への呼び出しを追加するには

1. メソッドにの呼び出しを追加して、Polyctl.htm を更新します。 `FireViewChange` `put_Sides` 完了すると、メソッドは次のようになり `put_Sides` ます。

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

追加した後 `FireViewChange` 、ActiveX コントロールテストコンテナーでもう一度コントロールをリビルドして、もう一度試してみてください。 今度は、辺の数を変更し、をクリックすると `Invoke` 、コントロールの変更がすぐに表示されます。

次の手順では、イベントを追加します。

手順[3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) . に戻り[、手順5に](../atl/adding-an-event-atl-tutorial-part-5.md)&#124; ます。

## <a name="see-also"></a>関連項目

[チュートリアル](../atl/active-template-library-atl-tutorial.md)<br/>
[テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)
