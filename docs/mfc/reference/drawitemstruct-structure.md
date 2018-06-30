---
title: DRAWITEMSTRUCT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DRAWITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff4596a52170d0c6d197a0bda431963b5f0e9344
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120939"
---
# <a name="drawitemstruct-structure"></a>DRAWITEMSTRUCT 構造体
`DRAWITEMSTRUCT` 構造体は、オーナー ウィンドウでオーナー描画コントロールまたはメニュー項目の描画方法を決定する情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagDRAWITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    UINT itemAction;  
    UINT itemState;  
    HWND hwndItem;  
    HDC hDC;  
    RECT rcItem;  
    DWORD itemData;  
} DRAWITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *CtlType*  
 コントロール型。 コントロール型の値は次のとおりです。  
  
- ODT_BUTTON オーナー描画ボタン  
  
- ODT_COMBOBOX オーナー描画コンボ ボックス  
  
- ODT_LISTBOX オーナー描画リスト ボックス  
  
- ODT_MENU オーナー描画メニュー  
  
- ODT_LISTVIEW リスト ビュー コントロール  
  
- ODT_STATIC オーナー描画スタティック コントロール  
  
- ODT_TAB タブ コントロール  
  
 *CtlID*  
 コンボ ボックス、リスト ボックスまたはボタンのコントロール ID。 このメンバーは、メニューには使用されません。  
  
 *itemID*  
 メニューのメニュー項目 ID、あるいはリスト ボックスまたはコンボ ボックス内の項目のインデックス。 空のリスト ボックスまたはコンボ ボックスは、このメンバーは、アプリケーションによって指定された座標にフォーカス四角形を描画するのには、負の値、`rcItem`コントロールで項目がない場合でもメンバー。 したがって、ユーザーはリスト ボックスまたはコンボ ボックスに入力フォーカスがあるかどうかを判断できます。 内のビットの設定、`itemAction`メンバーは、四角形がリスト ボックスまたはコンボ ボックスに入力フォーカスのように描画されるかどうかを決定します。  
  
 *ItemAction*  
 描画に必要なアクションを定義します。 これは次のビットの 1 つ以上になります。  
  
- ODA_DRAWENTIRE コントロール全体が描画されなければならないときに、このビットが設定されています。  
  
- ODA_FOCUS コントロールを取得したりが入力フォーカスを失ったときに、このビットが設定されています。 `itemState`メンバーをチェックして、コントロールにフォーカスがあるかどうかを決定する必要があります。  
  
- ODA_SELECT 選択状態のみが変更されたときに、このビットが設定されています。 `itemState`メンバーをチェックして、新しい選択状態を確認する必要があります。  
  
 *ItemState*  
 現在の描画アクションが実行された後の項目の表示状態を指定します。 つまり、メニュー項目が淡色表示する場合は、状態フラグ ODS_GRAYED 設定されます。 状態フラグは次のとおりです。  
  
- ODS_CHECKED メニュー項目をチェックする場合、このビットが設定されます。 このビットは、メニューでのみ使用されます。  
  
- ODS_DISABLED 項目が無効になっているように描画される場合、このビットが設定されます。  
  
- 項目に入力フォーカスがある場合、ODS_FOCUS このビットが設定されています。  
  
- ODS_GRAYED 項目が淡色表示する場合に、このビットが設定されます。 このビットは、メニューでのみ使用されます。  
  
- ODS_SELECTED 項目の状態が選択されている場合、このビットが設定されます。  
  
- ODS_COMBOBOXEDIT 図面は、オーナー描画コンボ ボックスの選択フィールド (エディット コントロール) で行われます。  
  
- ODS_DEFAULT アイテムとは、既定の項目です。  
  
 *hwndItem*  
 コンボ ボックス、リスト ボックス、およびボタンをコントロールするウィンドウ ハンドルを指定します。 メニュー項目を含むメニュー (HMENU) のハンドルを指定します。  
  
 *hDC*  
 デバイス コンテキストを識別します。 このデバイス コンテキストは、コントロール上で描画操作を実行するときに使用する必要があります。  
  
 *rcItem*  
 指定されたデバイス コンテキスト内の四角形、 *hDC*描画するコントロールの境界を定義するメンバー。 Windows では、コンボ ボックス、リスト、ボックス、およびボタン用にデバイス コンテキストにオーナーが描画したものすべてが自動的にクリップされますが、メニュー項目はクリップされません。 によって定義された四角形の境界の外側メニュー項目を描画するときに、所有者は描画できません、`rcItem`メンバー。  
  
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
  
## <a name="remarks"></a>Remarks  
 オーナー描画コントロールまたはメニュー項目のオーナー ウィンドウとしてこの構造体へのポインターを受け取る、 *lParam*ならなくのパラメーターです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

