---
title: リスト ボックス スタイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90441984aa8212212c3a9d4ea99cfb5b36127a03
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="list-box-styles"></a>リスト ボックス スタイル
-   **LBS_DISABLENOSCROLL**リスト ボックスが無効になっている、垂直スクロール バーと、リスト ボックスを含まないスクロールするための十分な項目を表示します。 このスタイルが設定されていないと、項目が少なくてスクロールする必要がない場合、スクロール バーは表示されません。  
  
-   **LBS_EXTENDEDSEL**ユーザーは、SHIFT キーとマウスまたは特殊なキーの組み合わせを使用して複数の項目を選択できます。  
  
-   **LBS_HASSTRINGS**文字列で構成される項目を含むオーナー描画リスト ボックスを指定します。 アプリケーションが使用できるように、リスト ボックス保持メモリと、文字列のポインター、`GetText`の特定のアイテムのテキストを取得します。  
  
-   **LBS_MULTICOLUMN**が水平方向にスクロールされる基準を複数列のリスト ボックスを指定します。 `SetColumnWidth`メンバー関数は、列の幅を設定します。  
  
-   **LBS_MULTIPLESEL**文字列選択が切り替えられたたびに、ユーザーがクリックするか、文字列をダブルクリックします。 文字列の任意の数を選択することができます。  
  
-   **LBS_NODATA**データなしのリスト ボックスを指定します。 リスト ボックス内の項目の数が 1,000 を超える場合は、このスタイルを指定します。 データなしのリスト ボックスがあります、 **LBS_OWNERDRAWFIXED**スタイルしますが、ない必要があります、 **LBS_SORT**または**LBS_HASSTRINGS**スタイル。  
  
     データなしのリスト ボックスではアイテムの文字列またはビットマップのデータが含まれていないする点を除いてオーナー描画リスト ボックスに似ています。 コマンドを追加するには、挿入、または項目を削除する常に指定した項目のデータをすべて無視します。常に、リスト ボックス内の文字列を検索する要求が失敗します。 システムは、送信、`WM_DRAWITEM`項目を描画する必要がある場合は、オーナー ウィンドウにメッセージ。 ItemID メンバー、`DRAWITEMSTRUCT`で構造体が渡される、`WM_DRAWITEM`メッセージが描画される項目の行番号を指定します。 データなしのリスト ボックスを送信しません、`WM_DELETEITEM`メッセージ。  
  
-   **LBS_NOINTEGRALHEIGHT**リスト ボックスのサイズは、リスト ボックスが作成されたときに、アプリケーションで指定されたサイズでは正確にします。 通常、Windows はリスト ボックス、リスト ボックスで一部の項目が表示されないようにするサイズを変更します。  
  
-   **LBS_NOREDRAW**変更が加えられた場合、リスト ボックスの表示は更新されません。 このスタイルは、送信することによっていつでも変更できる、 **WM_SETREDRAW**メッセージ。  
  
-   **LBS_NOSEL**リスト ボックスに表示することができますが、選択されていない項目が含まれているを指定します。  
  
-   **LBS_NOTIFY**親ウィンドウが、ユーザーがクリックするか、文字列をダブルクリックしたときに、入力メッセージを受け取ります。  
  
-   **LBS_OWNERDRAWFIXED**その内容を描画するため、リスト ボックスのオーナーが以外の場合は、リスト ボックス内の項目は同じ高さ。  
  
-   **LBS_OWNERDRAWVARIABLE**その内容を描画するため、リスト ボックスのオーナーが以外の場合は、リスト ボックス内の項目は高さ内の変数です。  
  
-   **LBS_SORT**リスト ボックス内の文字列はアルファベット順に並べ替えられます。  
  
-   **LBS_STANDARD**リスト ボックス内の文字列は、アルファベット順に並べ替えられ、ユーザーがクリックするか、文字列をダブルクリックしたときに、親ウィンドウが入力メッセージを受け取ります。 リスト ボックスには、すべての側面に罫線が含まれています。  
  
-   **LBS_USETABSTOPS**を認識し、その文字列を描画するときに、タブ文字を展開し、リスト ボックスを使用します。 既定のタブ位置は、32 のダイアログ単位です。 (ダイアログ単位は、水平または垂直距離です。 1 つの水平ダイアログ単位は、現在のダイアログ ベースの幅の単位の 4 分の 1 と同じです。 ダイアログの基本単位は、現在のシステム フォントの幅と高さに基づいて計算されます。 **GetDialogBaseUnits** Windows の機能はピクセル単位で現在のダイアログ ボックスの基本単位を返します)。このスタイルを使用しないで**LBS_OWNERDRAWFIXED**です。  
  
-   **LBS_WANTKEYBOARDINPUT** 、リスト ボックスの所有者は受信`WM_VKEYTOITEM`または`WM_CHARTOITEM`メッセージをリスト ボックスに入力フォーカスがある状態でキーを押したときにします。 これにより、キーボード入力に対して特別な処理を実行するアプリケーション。  
  
## <a name="see-also"></a>関連項目  
 [MFC によって使用されているスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [リスト ボックス スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775149)

