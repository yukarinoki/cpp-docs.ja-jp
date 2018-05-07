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
ms.openlocfilehash: bdb7daba666e8aaf983eadc77417cad46180e7df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
 `CtlType`  
 コントロール型。 コントロール型の値は次のとおりです。  
  
- **ODT_BUTTON** オーナー描画ボタン  
  
- **ODT_COMBOBOX** オーナー描画コンボ ボックス  
  
- **ODT_COMBOBOX** オーナー描画リスト ボックス  
  
- **ODT_MENU** オーナー描画メニュー  
  
- **ODT_LISTVIEW** リスト ビュー コントロール  
  
- **ODT_STATIC** オーナー描画スタティック コントロール  
  
- **ODT_TAB** タブ コントロール  
  
 `CtlID`  
 コンボ ボックス、リスト ボックスまたはボタンのコントロール ID。 このメンバーは、メニューには使用されません。  
  
 `itemID`  
 メニューのメニュー項目 ID、あるいはリスト ボックスまたはコンボ ボックス内の項目のインデックス。 このメンバーは、空のリスト ボックスまたはコンボ ボックスの場合は負の値であり、アプリケーションは、コントロールに項目がない場合でも、 **rcItem** メンバーで指定されている座標のフォーカスを表す四角形のみを描画します。 したがって、ユーザーはリスト ボックスまたはコンボ ボックスに入力フォーカスがあるかどうかを判断できます。 **itemAction** メンバー内のビットの設定によって、リスト ボックスまたはコンボ ボックスに入力フォーカスがあるものとして四角形を描画するかどうかが決まります。  
  
 `itemAction`  
 描画に必要なアクションを定義します。 これは次のビットの 1 つ以上になります。  
  
- **ODA_DRAWENTIRE** コントロール全体を描画する必要がある場合に設定されます。  
  
- **ODA_FOCUS** コントロールが入力フォーカスを取得したとき、または失ったときに設定されます。 **ItemState** メンバーは、コントロールにフォーカスがあるかどうかを判断する場合にチェックします。  
  
- **ODA_SELECT** 選択状態が変更された場合にのみ設定されます。 **itemState** メンバーは、選択状態が新しくなったかどうかを判断する場合にチェックします。  
  
 *ItemState*  
 現在の描画アクションが実行された後の項目の表示状態を指定します。 つまり、メニュー項目が淡色表示されている場合、状態フラグ **ODS_GRAYED** が設定されます。 状態フラグは次のとおりです。  
  
- **ODS_CHECKED** メニュー項目をチェックする場合に設定されます。 このビットは、メニューでのみ使用されます。  
  
- **ODS_DISABLED** 項目の描画が無効になっている場合に設定されます。  
  
- **ODS_FOCUS** 項目に入力フォーカスがある場合に設定されます。  
  
- **ODS_GRAYED** 項目が淡色表示される場合に設定されます。 このビットは、メニューでのみ使用されます。  
  
- **ODS_SELECTED** 項目の状態が選択されている場合に設定されます。  
  
- **ODS_COMBOBOXEDIT** オーナー描画のコンボ ボックスの選択項目 (エディット コントロール) で描画が実行されます。  
  
- **ODS_DEFAULT** 項目は既定の項目です。  
  
 `hwndItem`  
 コンボ ボックス、リスト ボックス、およびボタンをコントロールするウィンドウ ハンドルを指定します。 メニュー項目を含むメニューのハンドルを指定します (`HMENU`)。  
  
 `hDC`  
 デバイス コンテキストを識別します。 このデバイス コンテキストは、コントロール上で描画操作を実行するときに使用する必要があります。  
  
 *rcItem*  
 コントロールの境界を定義する `hDC` メンバーによってデバイス コンテキストを指定すると、そこに四角形が描画されます。 Windows では、コンボ ボックス、リスト、ボックス、およびボタン用にデバイス コンテキストにオーナーが描画したものすべてが自動的にクリップされますが、メニュー項目はクリップされません。 メニュー項目を描画する場合、オーナーは **rcItem** メンバーで定義した四角形の境界外には描画できません。  
  
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
  
## <a name="remarks"></a>コメント  
 オーナー描画コントロールのオーナー ウィンドウまたはメニュー項目は、この構造体へのポインターを `lParam` メッセージの `WM_DRAWITEM` パラメーターとして受け取ります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

