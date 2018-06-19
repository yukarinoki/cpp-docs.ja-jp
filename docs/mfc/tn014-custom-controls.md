---
title: 'TN014: カスタム コントロール |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls
dev_langs:
- C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54a7ef7f6fd9a9da92c208366ee401d55d07fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384583"
---
# <a name="tn014-custom-controls"></a>テクニカル ノート 14: カスタム コントロール
ここでは、カスタムおよび自己描画コントロールの MFC サポートについて説明します。 動的なサブクラス化をについて説明し、関係について説明[CWnd](../mfc/reference/cwnd-class.md)オブジェクトおよび`HWND`s。  
  
 CTRLTEST MFC サンプル アプリケーションは、多くのカスタム コントロールを使用する方法を示しています。 MFC 標準サンプルのソース コードを参照してください[CTRLTEST](../visual-cpp-samples.md)とオンラインのヘルプ。  
  
## <a name="owner-draw-controlsmenus"></a>オーナー描画コントロールまたはメニュー  
 Windows では、Windows メッセージを使用して、オーナー描画コントロールやメニューのサポートを提供します。 任意のコントロールまたはメニューの親ウィンドウは、応答のこれらのメッセージおよびコール関数を受け取ります。 オーナー描画コントロールまたはメニューの動作と外観をカスタマイズするこれらの関数をオーバーライドすることができます。  
  
 MFC は、オーナー描画直接サポートしています。 次の関数で。  
  
- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)  
  
- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)  
  
- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)  
  
- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)  
  
 これらの関数をオーバーライドすることができます、`CWnd`カスタム描画の動作を実装するクラスを派生します。  
  
 このアプローチが発生しても再利用可能なコードです。 2 つの異なる 2 つのようなコントロールがある場合`CWnd`クラス、2 つの場所にカスタム コントロールの動作を実装する必要があります。 自己描画コントロールの MFC でサポートされているアーキテクチャでは、この問題は解決します。  
  
## <a name="self-draw-controls-and-menus"></a>自己描画コントロールやメニュー  
 MFC には、既定の実装が用意されています (で、`CWnd`と[CMenu](../mfc/reference/cmenu-class.md)クラス) の標準のオーナー描画メッセージ。 この既定の実装がオーナー描画のパラメーターをデコードし、コントロールまたはメニューにオーナー描画メッセージを委任します。 自己描画と、描画コードがコントロールまたはメニューのオーナー ウィンドウではなくのクラスであるために、このようなこれは呼び出されます。  
  
 自己描画コントロールを使用してコントロールを表示するオーナー描画のセマンティクスを使用する再利用可能なコントロール クラスを作成できます。 コントロールの描画のコードは、コントロール クラス、親のないのです。 これは、カスタム コントロールのプログラミング オブジェクト指向アプローチです。 自己描画クラスに次の関数の一覧を追加します。  
  
-   自己描画ボタン。  
  
 ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw this button  
 ```  
  
-   自己描画メニュー。  
  
 ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this menu  
 ```  
  
-   自己描画リスト ボックス  
  
 ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this list box  
 
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this list box  
 ```  
  
-   自己描画のコンボ ボックス  
  
 ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this combo box  
 
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this combo box  
 ```  
  
 オーナー描画構造体の詳細 ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md)、 [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md)、 [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md)、および[DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) MFC のドキュメントを参照して`CWnd::OnDrawItem`、 `CWnd::OnMeasureItem`、 `CWnd::OnCompareItem`、および`CWnd::OnDeleteItem`それぞれします。  
  
## <a name="using-self-draw-controls-and-menus"></a>自己描画コントロールやメニューを使用  
 自己描画メニュー、両方をオーバーライドする必要があります、`OnMeasureItem`と`OnDrawItem`メソッドです。  
  
 オーバーライドする必要がありますの自己描画リスト ボックスやコンボ ボックス、`OnMeasureItem`と`OnDrawItem`です。 指定する必要があります、`LBS_OWNERDRAWVARIABLE`リスト ボックスのスタイルまたは`CBS_OWNERDRAWVARIABLE`スタイル コンボ ボックス ダイアログ テンプレート。 `OWNERDRAWFIXED`自己描画項目では、リスト ボックスに関連付けられているコントロールの自己描画前に、固定の項目の高さが決まるためスタイルは動作しません。 (メソッドを使用することができます[CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight)と[CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight)この制限を克服します)。  
  
 切り替え、`OWNERDRAWVARIABLE`スタイルが強制的に適用するシステム、`NOINTEGRALHEIGHT`コントロールにスタイル。 コントロールは、変数のサイズと整数の高さを計算できませんので項目、既定のスタイルの`INTEGRALHEIGHT`は無視されます、コントロールが常に`NOINTEGRALHEIGHT`です。 アイテムの高さ固定である場合、コントロールのサイズの項目のサイズの整数乗数を指定することで描画されるから部分的な項目ができなくなります。  
  
 自己リスト ボックスやコンボ ボックスを描画するため、`LBS_SORT`または`CBS_SORT`スタイルをオーバーライドする必要がある、`OnCompareItem`メソッドです。  
  
 自己描画リスト ボックスやコンボ ボックス、`OnDeleteItem`は通常、オーバーライドできません。 オーバーライドできます`OnDeleteItem`特別な処理を実行する場合。 該当する 1 つのケースは、追加のメモリやその他のリソースが各リスト ボックスまたはコンボ ボックスの項目に格納されている場合です。  
  
## <a name="examples-of-self-drawing-controls-and-menus"></a>自己描画コントロールやメニューの例  
 MFC 標準サンプル[CTRLTEST](../visual-cpp-samples.md)自己描画メニューと自己描画リスト ボックスの例を示します。  
  
 自己描画ボタンの最も一般的な例は、ビットマップ ボタンです。 ビットマップのボタンは、さまざまな状態の 1 つ、2 つ、または 3 つのビットマップ イメージを表示するボタンです。 この例は、MFC クラスで提供される[CBitmapButton](../mfc/reference/cbitmapbutton-class.md)です。  
  
## <a name="dynamic-subclassing"></a>動的なサブクラス化  
 場合によっては、既に存在するオブジェクトの機能を変更するされます。 前の例には、作成された前に、コントロールをカスタマイズすることが必要です。 動的なサブクラス化では、既に作成されているコントロールをカスタマイズすることができます。  
  
 サブクラスは、Windows 用語の置換、 [WndProc](http://msdn.microsoft.com/en-us/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26)カスタマイズされたウィンドウの`WndProc`および呼び出し、古い`WndProc`の既定の機能です。  
  
 これは、必要がありますと混同しない C++ クラスから派生します。 わかりやすいように、C++ の用語*基底クラス*と*クラスを派生*に似ています*スーパークラス*と*サブクラス*windowsオブジェクト モデル。 C++ では、動的なサブクラス化をサポートしていません点を除いて、MFC と Windows のサブクラス化における C++ の派生は機能的によく似たです。  
  
 `CWnd`クラスには、C++ オブジェクトの間の接続が用意されています (から派生した`CWnd`) と Windows ウィンドウ オブジェクト (と呼ばれる、 `HWND`)。  
  
 これらの関係は次の 3 つの一般的な方法があります。  
  
- `CWnd` 作成、`HWND`です。 派生するクラスを作成することで、派生クラスで動作を変更することができます`CWnd`です。 `HWND`アプリケーションが呼び出すときに作成される[cwnd::create](../mfc/reference/cwnd-class.md#create)です。  
  
-   アプリケーションのアタッチ、`CWnd`既存`HWND`です。 既存のウィンドウの動作は変更されません。 これは、委任のケースであり、呼び出すことによって可能になりますが[CWnd::Attach](../mfc/reference/cwnd-class.md#attach)既存エイリアス`HWND`を`CWnd`オブジェクト。  
  
- `CWnd` 既存にアタッチされて`HWND`および派生クラスでの動作を変更できます。 これは、動的なサブクラス化動作とそのため、実行時に Windows のオブジェクトのクラスを変更しているために呼び出されます。  
  
 動的なサブクラス化を行うには、メソッドを使用して[CWnd::SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow)と[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)です。  
  
 2 つのルーチンのアタッチ、`CWnd`を既存のオブジェクト`HWND`です。 `SubclassWindow` `HWND`直接です。 `SubclassDlgItem` コントロールの ID と親ウィンドウを受け取るヘルパー関数です。 `SubclassDlgItem` ダイアログ コントロールにダイアログ テンプレートから作成された C++ オブジェクトのアタッチされています。  
  
 参照してください、 [CTRLTEST](../visual-cpp-samples.md)を使用する場合の例をいくつかの例を`SubclassWindow`と`SubclassDlgItem`です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

