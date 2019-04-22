---
title: TN014:カスタム コントロール
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: c68b60f065e69213b3ab32c887bc7af129a70fef
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772125"
---
# <a name="tn014-custom-controls"></a>TN014:カスタム コントロール

ここでは、カスタムおよび自己描画コントロール MFC サポートについて説明します。 動的なサブクラス化について説明しの間のリレーションシップについて説明します[CWnd](../mfc/reference/cwnd-class.md)オブジェクトと`HWND`秒。

CTRLTEST MFC サンプル アプリケーションは、多くのカスタム コントロールを使用する方法を示しています。 MFC 標準サンプルのソース コードを参照してください。 [CTRLTEST](../overview/visual-cpp-samples.md)とオンライン ヘルプ。

## <a name="owner-draw-controlsmenus"></a>オーナー描画コントロールまたはメニュー

Windows は、Windows メッセージを使用して、オーナー描画コントロールやメニューのサポートを提供します。 任意のコントロールまたはメニューの親ウィンドウは、応答でこれらのメッセージと呼び出し関数を受け取ります。 オーナー描画コントロールまたはメニューの動作と外観をカスタマイズするこれらの関数をオーバーライドすることができます。

MFC は、オーナー描画直接サポートしています。 次の関数で。

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

これらの関数をオーバーライドすることができます、`CWnd`カスタム描画の動作を実装するクラスを派生します。

このアプローチはコードの再利用可能な発生しません。 2 つの異なる 2 つのようなコントロールがある場合`CWnd`クラス、2 つの場所にカスタム コントロールの動作を実装する必要があります。 自己描画コントロールの MFC でサポートされているアーキテクチャでは、この問題は解決します。

## <a name="self-draw-controls-and-menus"></a>自己描画コントロールやメニュー

MFC には、既定の実装が用意されています (で、`CWnd`と[CMenu](../mfc/reference/cmenu-class.md)クラス) の標準のオーナー描画メッセージ。 この既定の実装はオーナー描画のパラメーターをデコードし、コントロールまたはメニューにオーナー描画メッセージを委任します。 描画のコードがオーナー ウィンドウではなく、メニューのコントロールのクラスのためは、自己描画この呼び出されます。

自己描画コントロールを使用して、オーナー描画のセマンティクスを使用して、コントロールを表示する再利用可能なコントロール クラスを構築できます。 コントロールを描画するためのコードでは、コントロール クラス、その親ではありません。 これは、カスタム コントロールのプログラミング、オブジェクト指向手法です。 自己描画クラスには、次の関数の一覧を追加します。

- 自己描画ボタン。

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- 自己描画メニュー。

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- 自己描画リスト ボックス。

    ```cpp
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this list box
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this list box

    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this list box if LBS_SORT
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this list box
    ```

- 自己描画のコンボ ボックス

    ```cpp
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this combo box
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this combo box

    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this combo box if CBS_SORT
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this combo box
    ```

詳細については、オーナー描画の構造に ([DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)、 [MEASUREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagmeasureitemstruct)、 [COMPAREITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcompareitemstruct)、および[DELETEITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdeleteitemstruct)) MFC のドキュメントを参照して`CWnd::OnDrawItem`、 `CWnd::OnMeasureItem`、 `CWnd::OnCompareItem`、および`CWnd::OnDeleteItem`それぞれします。

## <a name="using-self-draw-controls-and-menus"></a>自己描画コントロールとメニューを使用

自己描画メニューで、両方をオーバーライドする必要があります、`OnMeasureItem`と`OnDrawItem`メソッド。

自己描画リスト ボックスやコンボ ボックスでは、オーバーライドする必要があります`OnMeasureItem`と`OnDrawItem`します。 ダイアログ テンプレートでは、LBS_OWNERDRAWVARIABLE スタイルのリスト ボックスまたはコンボ ボックスの CBS_OWNERDRAWVARIABLE スタイルを指定する必要があります。 OWNERDRAWFIXED スタイルは自己描画コントロールは、リスト ボックスに関連付けられている前に固定の項目の高さが決定されるため、自己描画項目では機能しません。 (メソッドを使用する[CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight)と[CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight)この制限を克服するためにします)。

OWNERDRAWVARIABLE スタイルに切り替え、NOINTEGRALHEIGHT スタイル コントロールを適用するシステムが実行されます。 コントロールは、変数のサイズが設定された項目を含む整数の高さを計算することはできません、ため INTEGRALHEIGHT の既定のスタイルは無視され、コントロールが NOINTEGRALHEIGHT では常に。 場合は、アイテムの高さは固定で一部の項目を防ぐために、整数の乗数、アイテムのサイズのコントロールのサイズを指定することで描画することができます。

自己リスト ボックスや、LBS_SORT または CBS_SORT スタイルのコンボ ボックスを描画、オーバーライドする必要があります、`OnCompareItem`メソッド。

自己描画リスト ボックスやコンボ ボックス、`OnDeleteItem`は通常、オーバーライドできません。 オーバーライドできます`OnDeleteItem`特別な処理を実行したい場合。 場合が考えは、追加のメモリやその他のリソースがリスト ボックスまたはコンボ ボックスの項目ごとに格納されている場合です。

## <a name="examples-of-self-drawing-controls-and-menus"></a>自己コントロールやメニューを描画の例

MFC 標準サンプル[CTRLTEST](../overview/visual-cpp-samples.md)自己描画メニューと自己描画リスト ボックスのサンプルを提供します。

自己描画ボタンの最も一般的な例は、ビットマップ ボタンです。 ビットマップのボタンは、各状態用に 1 つ、2 つ、または 3 つのビットマップ イメージを表示するボタンです。 この例は MFC クラスで提供される[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)します。

## <a name="dynamic-subclassing"></a>動的なサブクラス化

既に存在するオブジェクトの機能を変更することがあります。 前の例には、作成された前に、コントロールをカスタマイズすることが必要です。 動的なサブクラス化では、既に作成されているコントロールをカスタマイズすることができます。

サブクラス化は、Windows という用語を置換するため、<xref:System.Windows.Forms.Control.WndProc%2A>カスタマイズされたウィンドウの`WndProc`古いを呼び出すと`WndProc`の既定の機能です。

これと混同しない C++ クラスの派生です。 詳細については、C++ の用語*基本クラス*と*クラスを派生*に似ています*スーパークラス*と*サブクラス*Windows でオブジェクト モデル。 MFC と Windows のサブクラス化における C++ の派生が、機能的によく似た、C++ では、動的なサブクラス化をサポートしていません。

`CWnd`クラスが C++ オブジェクト間の接続を提供します (から派生した`CWnd`) と Windows のウィンドウ オブジェクト (と呼ばれる、 `HWND`)。

これらに関連する 3 つの一般的な方法があります。

- `CWnd` 作成、`HWND`します。 派生クラスで動作を変更するにはから派生したクラスを作成して`CWnd`します。 `HWND`アプリケーションを呼び出すときに作成されます[cwnd::create](../mfc/reference/cwnd-class.md#create)します。

- アプリケーションの接続、`CWnd`既存`HWND`します。 既存のウィンドウの動作は変更されません。 これは、場合、委任と呼び出すことによって実現されます[CWnd::Attach](../mfc/reference/cwnd-class.md#attach)既存エイリアス`HWND`を`CWnd`オブジェクト。

- `CWnd` 既存の接続は`HWND`と派生クラスで動作を変更することができます。 これは、動的な動作とそのため、実行時に Windows のオブジェクトのクラスを変更しているため、サブクラス化で呼び出されます。

メソッドを使用して動的なサブクラス化を実現できる[CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow)と[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)します。

2 つのルーチンのアタッチ、`CWnd`を既存のオブジェクト`HWND`します。 `SubclassWindow` `HWND`直接します。 `SubclassDlgItem` ヘルパー関数は、コントロールの ID と親ウィンドウです。 `SubclassDlgItem` ダイアログ テンプレートから作成されたダイアログ コントロールに C++ オブジェクトをアタッチされています。

参照してください、 [CTRLTEST](../overview/visual-cpp-samples.md)を使用する場合の例をいくつかの例を`SubclassWindow`と`SubclassDlgItem`します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
