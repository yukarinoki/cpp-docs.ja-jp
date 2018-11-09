---
title: ダイアログ ボックス コントロールおよび変数の型
ms.date: 11/04/2016
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
ms.openlocfilehash: efacd6382d5773c4c47896a99910d9fe9934397a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600124"
---
# <a name="dialog-box-controls-and-variable-types"></a>ダイアログ ボックス コントロールおよび変数の型

[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)を使用すると、MFC で作成したダイアログ ボックス コントロールにメンバー変数を追加できます。 メンバー変数を追加するコントロールの種類によって、ダイアログ ボックスに表示されるオプションが決まります。

次の表は、MFC と[ダイアログ エディター](../windows/dialog-editor.md)でサポートされているすべてのダイアログ ボックス コントロール、選択できる種類と値をまとめたものです。

|コントロール|コントロールの種類|コントロール変数の型|値変数の型|最小/最大値 (値の型のみ)|
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|
|アニメーション コントロール|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|なし、コントロールのみ|N/A|
|ボタン|ボタン|[CButton](../mfc/reference/cbutton-class.md)|なし、コントロールのみ|N/A|
|チェック ボックス|チェック|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|最小値/最大値|
|コンボ ボックス|コンボ ボックス|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|最大文字数|
|日時指定コントロール|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|最小値/最大値|
|エディット ボックス|編集|[CEdit](../mfc/reference/cedit-class.md)|`CString`、int、UINT、long、DWORD、float、double、BYTE、short、BOOL、`COleDateTime`、**COleCurrency**|最小値/最大値、一部は最大文字数をサポート|
|ホット キー コントロール|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|なし、コントロールのみ|N/A|
|リスト ボックス|リスト ボックス|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|最大文字数|
|リスト コントロール|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|なし、コントロールのみ|N/A|
|月間予定表コントロール|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|最小値/最大値|
|プログレス コントロール|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|なし、コントロールのみ|N/A|
|リッチ エディット 2 コントロール|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|最大文字数|
|リッチ エディット コントロール|RICHEDIT|`CRichEditCtrl`|`CString`|最大文字数|
|スクロール バー (垂直または水平)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|最小値/最大値|
|スライダー コントロール|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|最小値/最大値|
|スピン コントロール|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|なし、コントロールのみ|N/A|
|タブ コントロール|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|なし、コントロールのみ|N/A|
|ツリー コントロール|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|なし、コントロールのみ|N/A|

## <a name="see-also"></a>参照

[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)