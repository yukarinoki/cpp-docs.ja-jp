---
title: MEASUREITEMSTRUCT 構造体 |Microsoft Docs
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
ms.openlocfilehash: bcf4bd41d00f6999b4158f0884c39e7a16d10bcc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336960"
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT 構造体
`MEASUREITEMSTRUCT`構造オーナー描画コントロールまたはメニュー項目のサイズの Windows に通知します。  
  
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
 *CtlType*  
 コントロールの種類が含まれています。 コントロール型の値は次のとおりです。  
  
- ODT_COMBOBOX オーナー描画コンボ ボックス  
  
- ODT_LISTBOX オーナー描画リスト ボックス  
  
- ODT_MENU オーナー描画メニュー  
  
 *CtlID*  
 コンボ ボックス、リスト ボックス、またはボタンのコントロール ID が含まれています。 このメンバーは、メニューには使用されません。  
  
 *アイテム Id*  
 メニューのメニュー項目の ID または可変高ボックスまたはリスト ボックスのリスト ボックス項目 ID が含まれています。 このメンバーは、固定サイズのコンボ ボックスまたはリスト ボックスまたはボタンは使用されません。  
  
 *itemWidth*  
 メニュー項目の幅を指定します。 オーナー描画メニュー項目の所有者は、メッセージから返す前に、このメンバーを入力する必要があります。  
  
 *itemHeight*  
 リスト ボックスまたはメニューで、個々 の項目の高さを指定します。 メッセージをオーナー描画コンボ ボックスの所有者を返す前に、リスト ボックス、またはメニュー項目がこのメンバーを入力する必要があります。 リスト ボックス アイテムの高さの最大値は、255 です。  
  
 *取得*  
 コンボ ボックスまたはリスト ボックスでは、次のいずれかによってリスト ボックスに渡された値がメンバーに含まれています。  
  
- [CComboBox::AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 メニューでは、次のいずれかによってメニューに渡された値がメンバーに含まれています。  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 これにより、Windows コントロールにユーザーの操作を正しく処理できます。 障害に適切なメンバーの入力を`MEASUREITEMSTRUCT`構造体には、コントロールの不適切な操作が発生します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

