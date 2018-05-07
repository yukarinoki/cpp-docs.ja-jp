---
title: ダイアログ ボックス コントロールおよび変数の型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2fbae37072f50898181334a9059a7dc9c6a83a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dialog-box-controls-and-variable-types"></a>ダイアログ ボックス コントロールおよび変数の型
使用することができます、[メンバー変数の追加ウィザード](../ide/add-member-variable-wizard.md)MFC を使用して作成 ダイアログ ボックス コントロールにメンバー変数を追加します。 メンバー変数を追加するコントロールの種類では、ダイアログ ボックスに表示されるオプションを決定します。  
  
 次の表に、MFC でサポートされるすべてのダイアログ ボックス コントロール型と[ダイアログ エディター](../windows/dialog-editor.md)、およびその使用可能な型と値。  
  
|コントロール|コントロールの種類|コントロール変数の型|変数の型の値|最小/最大値 (値型のみ)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|アニメーション コントロール|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|[なし] です。コントロールのみ|N/A|  
|ボタン|ボタン|[CButton](../mfc/reference/cbutton-class.md)|[なし] です。コントロールのみ|N/A|  
|チェック ボックス|チェック|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|最小値/最大値|  
|コンボ ボックス|コンボ ボックス|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|最大文字数|  
|日時指定コントロール|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|最小値/最大値|  
|エディット ボックス|編集|[CEdit](../mfc/reference/cedit-class.md)|`CString`、int、UINT、long、DWORD、float、double、BYTE、short、BOOL、 `COleDateTime`、または**COleCurrency**|最小値/最大値です。サポートの一部の最大文字|  
|ホット キー コントロール|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|[なし] です。コントロールのみ|N/A|  
|リスト ボックス|リスト ボックス|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|最大文字数|  
|リスト コントロール|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|[なし] です。コントロールのみ|N/A|  
|月間予定表コントロール|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|最小値/最大値|  
|プログレス コントロール|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|[なし] です。コントロールのみ|N/A|  
|リッチ エディット 2 コントロール|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|最大文字数|  
|リッチ エディット コントロール|リッチ エディット|`CRichEditCtrl`|`CString`|最大文字数|  
|(水平または垂直スクロール バー|スクロール バー|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|最小値/最大値|  
|スライダー コントロール|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|最小値/最大値|  
|スピン コントロール|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|[なし] です。コントロールのみ|N/A|  
|タブ コントロール|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|[なし] です。コントロールのみ|N/A|  
|ツリー コントロール|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|[なし] です。コントロールのみ|N/A|  
  
## <a name="see-also"></a>関連項目  
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)