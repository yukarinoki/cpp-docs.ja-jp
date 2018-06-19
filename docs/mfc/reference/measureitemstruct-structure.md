---
title: MEASUREITEMSTRUCT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MEASUREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff015fdaf9e37d919459cadc8e4c35c4b795b3f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372271"
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT 構造体
`MEASUREITEMSTRUCT`構造オーナー描画コントロールまたはメニュー項目のサイズのウィンドウに通知します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagMEASUREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemWidth;  
    UINT itemHeight;  
    DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CtlType`  
 コントロールの種類が含まれています。 コントロール型の値は次のとおりです。  
  
- **ODT_COMBOBOX**オーナー描画コンボ ボックス  
  
- **ODT_LISTBOX**オーナー描画リスト ボックス  
  
- **ODT_MENU**オーナー描画メニュー  
  
 `CtlID`  
 コンボ ボックス、リスト ボックスまたはボタンのコントロール ID が含まれています。 このメンバーは、メニューには使用されません。  
  
 `itemID`  
 メニューのメニュー項目の ID または可変高コンボ ボックスまたはリスト ボックスのリスト ボックス項目 ID が含まれています。 このメンバーは、高さ固定のコンボ ボックスまたはリスト ボックスやボタンは使用されません。  
  
 *itemWidth*  
 メニュー項目の幅を指定します。 オーナー描画メニュー項目の所有者は、返されるメッセージの前に、このメンバーを読み込む必要があります。  
  
 *itemHeight*  
 リスト ボックスまたはメニューで、個々 の項目の高さを指定します。 メッセージをオーナー描画コンボ ボックスの所有者を返す前にリスト ボックス、またはメニュー項目を入力するこのメンバー。 リスト ボックス項目の高さの最大値は 255 です。  
  
 `itemData`  
 コンボ ボックスまたはリスト ボックスでは、次のいずれかによってリスト ボックスに渡された値がメンバーに含まれています。  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 メニューでは、次のいずれかによってメニューに渡された値がメンバーに含まれています。  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 これにより、Windows がコントロールでのユーザー操作を正しく処理できます。 適切なメンバーに記入エラー、`MEASUREITEMSTRUCT`構造体には、コントロールの不適切な操作が発生します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

