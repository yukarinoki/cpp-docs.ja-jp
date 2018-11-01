---
title: DRAWITEMSTRUCT 構造体
ms.date: 11/04/2016
f1_keywords:
- DRAWITEMSTRUCT
helpviewer_keywords:
- DRAWITEMSTRUCT structure [MFC]
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
ms.openlocfilehash: 9c5bfc12bd371761682102dad6d7bcb75ef44151
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624433"
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

*CtlType*<br/>
コントロール型。 コントロール型の値は次のとおりです。

- ODT_BUTTON オーナー描画ボタン

- ODT_COMBOBOX オーナー描画コンボ ボックス

- ODT_LISTBOX オーナー描画リスト ボックス

- ODT_MENU オーナー描画メニュー

- ODT_LISTVIEW リスト ビュー コントロール

- ODT_STATIC オーナー描画スタティック コントロール

- ODT_TAB タブ コントロール

*CtlID*<br/>
コンボ ボックス、リスト ボックスまたはボタンのコントロール ID。 このメンバーは、メニューには使用されません。

*アイテム Id*<br/>
メニューのメニュー項目 ID、あるいはリスト ボックスまたはコンボ ボックス内の項目のインデックス。 このメンバーは、アプリケーションによって指定された座標にフォーカス四角形を描画するのには、負の値を空のリスト ボックスまたはコンボ ボックスに、`rcItem`コントロールで項目がない場合でもメンバー。 したがって、ユーザーはリスト ボックスまたはコンボ ボックスに入力フォーカスがあるかどうかを判断できます。 内のビットの設定、`itemAction`メンバーは、四角形がリスト ボックスまたはコンボ ボックスに入力フォーカスのように描画されるかどうかを決定します。

*itemAction*<br/>
描画に必要なアクションを定義します。 これは次のビットの 1 つ以上になります。

- ODA_DRAWENTIRE コントロール全体を描画する必要がある場合、このビットが設定されています。

- ODA_FOCUS コントロールを取得したりが入力フォーカスを失ったときに、このビットが設定されています。 `itemState`メンバーをチェックして、コントロールにフォーカスがあるかどうかを判断する必要があります。

- ODA_SELECT 選択状態のみが変更されたときに、このビットが設定されます。 `itemState`メンバーをチェックして、新しい選択状態を確認する必要があります。

*ItemState*<br/>
現在の描画アクションが実行された後の項目の表示状態を指定します。 つまり、メニュー項目が淡色表示される場合は、状態フラグ ODS_GRAYED は設定されます。 状態フラグは次のとおりです。

- ODS_CHECKED メニュー項目がチェックする場合、このビットが設定されます。 このビットは、メニューでのみ使用されます。

- ODS_DISABLED 項目が無効になっているように描画される場合、このビットが設定されます。

- ODS_FOCUS このビットは、項目に入力フォーカスがある場合に設定されます。

- ODS_GRAYED 項目が淡色表示される場合、このビットが設定されます。 このビットは、メニューでのみ使用されます。

- ODS_SELECTED 項目の状態が選択されている場合、このビットが設定されます。

- ODS_COMBOBOXEDIT 図面は、オーナー描画のコンボ ボックスの選択フィールド (エディット コントロール) で行われます。

- ODS_DEFAULT 項目は、既定の項目です。

*hwndItem*<br/>
コンボ ボックス、リスト ボックス、およびボタンをコントロールするウィンドウ ハンドルを指定します。 メニュー項目を含むメニュー (HMENU) のハンドルを指定します。

*hDC*<br/>
デバイス コンテキストを識別します。 このデバイス コンテキストは、コントロール上で描画操作を実行するときに使用する必要があります。

*rcItem*<br/>
指定されたデバイス コンテキスト内の四角形、 *hDC*のコントロールを描画する境界を定義するメンバー。 Windows では、コンボ ボックス、リスト、ボックス、およびボタン用にデバイス コンテキストにオーナーが描画したものすべてが自動的にクリップされますが、メニュー項目はクリップされません。 によって定義された四角形の境界の外に、所有者は描画できませんメニュー項目を描画するときに、`rcItem`メンバー。

*取得*<br/>
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

オーナー描画コントロールまたはメニュー項目のオーナー ウィンドウとしてこの構造体へのポインターを受け取る、 *lParam*ならなくのパラメーター。

## <a name="requirements"></a>必要条件

**ヘッダー:** winuser.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem)

