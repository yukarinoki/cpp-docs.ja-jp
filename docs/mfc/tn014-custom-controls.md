---
description: '詳細情報: テクニカルノート 14: カスタムコントロール'
title: 'テクニカル ノート 14: カスタム コントロール'
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: c9b069e0101b279558c5bcd4ffb7f457120e8187
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215977"
---
# <a name="tn014-custom-controls"></a>テクニカル ノート 14: カスタム コントロール

このメモでは、カスタムコントロールと自己描画コントロールの MFC サポートについて説明します。 また、動的サブクラス化についても説明し、 [CWnd](../mfc/reference/cwnd-class.md) オブジェクトと s の関係について説明し `HWND` ます。

MFC サンプルアプリケーション CTRLTEST は、多くのカスタムコントロールの使用方法を示しています。 MFC の一般的なサンプル [CTRLTEST](../overview/visual-cpp-samples.md) とオンラインヘルプのソースコードを参照してください。

## <a name="owner-draw-controlsmenus"></a>Owner-Draw コントロール/メニュー

Windows では、Windows メッセージを使用したオーナー描画コントロールとメニューがサポートされています。 コントロールまたはメニューの親ウィンドウは、これらのメッセージを受信し、応答として関数を呼び出します。 これらの関数をオーバーライドすると、オーナー描画コントロールまたはメニューの外観と動作をカスタマイズできます。

MFC では、次の関数を使用したオーナー描画が直接サポートされています。

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

派生クラスでこれらの関数をオーバーライドすると、 `CWnd` カスタムの描画動作を実装できます。

この方法は、再利用可能なコードにはつながりません。 2つの異なるクラスに2つの類似したコントロールがある場合は、 `CWnd` カスタムコントロールの動作を2つの場所に実装する必要があります。 MFC でサポートされている自己描画コントロールアーキテクチャは、この問題を解決します。

## <a name="self-draw-controls-and-menus"></a>Self-Draw コントロールとメニュー

MFC では、 `CWnd` 標準のオーナー描画メッセージ用に既定の実装 (および [CMenu](../mfc/reference/cmenu-class.md) クラス) が用意されています。 この既定の実装では、オーナー描画パラメーターをデコードし、オーナー描画メッセージをコントロールまたはメニューに委任します。 これは、描画コードが [オーナー] ウィンドウではなく、コントロールまたはメニューのクラスにあるため、自己描画と呼ばれます。

自己描画コントロールを使用すると、オーナー描画のセマンティクスを使用してコントロールを表示する再利用可能なコントロールクラスを構築できます。 コントロールを描画するためのコードは、その親ではなく、コントロールクラスに含まれています。 これは、カスタムコントロールプログラミングに対するオブジェクト指向のアプローチです。 自己描画クラスに次の関数の一覧を追加します。

- 自己描画ボタンの場合:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- 自己描画メニューの場合:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- 自己描画リストボックスの場合:

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

- 自己描画コンボボックスの場合:

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

オーナー描画構造 ([DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct)、 [MEASUREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-measureitemstruct)、 [COMPAREITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-compareitemstruct)、および [DELETEITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)) の詳細については `CWnd::OnDrawItem` 、それぞれ、、 `CWnd::OnMeasureItem` `CWnd::OnCompareItem` 、およびの MFC ドキュメントを参照してください `CWnd::OnDeleteItem` 。

## <a name="using-self-draw-controls-and-menus"></a>自己描画コントロールとメニューの使用

自己描画メニューの場合は、メソッドとメソッドの両方をオーバーライドする必要があり `OnMeasureItem` `OnDrawItem` ます。

自己描画リストボックスとコンボボックスの場合は、およびをオーバーライドする必要があり `OnMeasureItem` `OnDrawItem` ます。 ダイアログテンプレートでは、コンボボックスのリストボックスまたは CBS_OWNERDRAWVARIABLE スタイルに LBS_OWNERDRAWVARIABLE スタイルを指定する必要があります。 固定項目の高さは、自己描画コントロールがリストボックスにアタッチされる前に決定されるため、OWNERDRAWFIXED スタイルは自己描画項目では機能しません。 (この制限を克服するには、 [CListBox:: SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) メソッドと [CComboBox:: SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) メソッドを使用できます)。

OWNERDRAWVARIABLE スタイルに切り替えると、システムが NOインテグレーション ALHEIGHT スタイルをコントロールに適用するように強制されます。 コントロールでは、可変サイズの項目を使用して整数の高さを計算できないので、既定のスタイルである型の既定のスタイルは無視され、コントロールは常に NOインテグレーション ALHEIGHT になります。 項目の高さが固定されている場合は、項目サイズの整数乗数としてコントロールのサイズを指定することで、部分的な項目が描画されないようにすることができます。

LBS_SORT または CBS_SORT スタイルを持つ自己描画のリストボックスとコンボボックスについては、メソッドをオーバーライドする必要があり `OnCompareItem` ます。

自己描画のリストボックスやコンボボックスの場合、 `OnDeleteItem` 通常はオーバーライドされません。 `OnDeleteItem`特別な処理を実行する場合は、をオーバーライドできます。 これが適用されるケースの1つは、追加のメモリまたはその他のリソースが各リストボックスまたはコンボボックス項目と共に格納されている場合です。

## <a name="examples-of-self-drawing-controls-and-menus"></a>Self-Drawing コントロールとメニューの例

MFC の一般的なサンプル [CTRLTEST](../overview/visual-cpp-samples.md) では、自己描画メニューと自己描画リストボックスのサンプルが提供されています。

自己描画ボタンの最も一般的な例は、ビットマップボタンです。 ビットマップボタンは、状態が異なる1つ、2つ、または3つのビットマップイメージを表示するボタンです。 この例については、MFC クラスの [Cbitmapbutton](../mfc/reference/cbitmapbutton-class.md)を使用します。

## <a name="dynamic-subclassing"></a>動的なサブクラス化

場合によっては、既に存在するオブジェクトの機能を変更する必要があります。 前の例では、コントロールを作成する前にカスタマイズする必要がありました。 動的サブクラス化を使用すると、既に作成されているコントロールをカスタマイズできます。

サブクラス化は、 <xref:System.Windows.Forms.Control.WndProc%2A> ウィンドウのをカスタマイズして、 `WndProc` `WndProc` 既定の機能を呼び出すための Windows 用語です。

これは、C++ クラスの派生と混同しないようにしてください。 説明を明確にするために、C++ 用語の *基本クラス* と *派生クラス* は、Windows オブジェクトモデルの *スーパー* クラスと *サブ* クラスに似ています。 MFC と Windows のサブクラス化による c++ の派生は機能的には似ていますが、C++ では動的サブクラス化がサポートされていません。

クラスは、 `CWnd` C++ オブジェクト (から派生 `CWnd` ) と Windows ウィンドウオブジェクト (と呼ばれます) の間の接続を提供し `HWND` ます。

次の3つの一般的な関連する方法があります。

- `CWnd` を作成し `HWND` ます。 派生クラスの動作は、から派生したクラスを作成することによって変更でき `CWnd` ます。 `HWND`アプリケーションが[CWnd:: Create](../mfc/reference/cwnd-class.md#create)を呼び出すと、が作成されます。

- アプリケーションは、を `CWnd` 既存のにアタッチし `HWND` ます。 既存のウィンドウの動作は変更されません。 これは委任のケースであり、 [CWnd:: Attach](../mfc/reference/cwnd-class.md#attach) を呼び出して、既存 `HWND` のオブジェクトに対するエイリアスのエイリアスを作成することによって可能になります `CWnd` 。

- `CWnd` は、既存のにアタッチされ、 `HWND` 派生クラスで動作を変更できます。 これを動的サブクラス化と呼びます。これは、実行時に Windows オブジェクトの動作、つまりクラスを変更するためです。

[Cwnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow)メソッドと[Cwnd:: SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)メソッドを使用して、動的なサブクラス化を実現できます。

どちらのルーチンも `CWnd` 、オブジェクトを既存のにアタッチ `HWND` します。 `SubclassWindow` を `HWND` 直接受け取ります。 `SubclassDlgItem` は、コントロール ID と親ウィンドウを受け取るヘルパー関数です。 `SubclassDlgItem` は、ダイアログテンプレートから作成されたダイアログコントロールに C++ オブジェクトをアタッチするように設計されています。

とを使用する場合の例については、 [CTRLTEST](../overview/visual-cpp-samples.md) の例を参照してください `SubclassWindow` `SubclassDlgItem` 。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
