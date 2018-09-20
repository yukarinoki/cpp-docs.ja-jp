---
title: DELETEITEMSTRUCT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb5b9d710bef136893c66208480056f6bc6390d3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429709"
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT 構造体

`DELETEITEMSTRUCT`構造体が、削除されたオーナー描画リスト ボックスまたはコンボ ボックス項目について説明します。

## <a name="syntax"></a>構文

```
typedef struct tagDELETEITEMSTRUCT { /* ditms */
    UINT CtlType;
    UINT CtlID;
    UINT itemID;
    HWND hwndItem;
    UINT itemData;
} DELETEITEMSTRUCT;
```

#### <a name="parameters"></a>パラメーター

*CtlType*<br/>
ODT_LISTBOX (オーナー描画リスト ボックス、) または ODT_COMBOBOX (オーナー描画コンボ ボックス、) を指定します。

*CtlID*<br/>
リスト ボックスまたはコンボ ボックスの識別子を指定します。

*アイテム Id*<br/>
リスト ボックスまたはコンボ ボックスの削除された項目のインデックスを指定します。

*hwndItem*<br/>
コントロールを識別します。

*取得*<br/>
項目のデータをアプリケーション定義を指定します。 この値は、コントロールで、 *lParam*項目をリスト ボックスまたはコンボ ボックスに追加するメッセージのパラメーター。

## <a name="remarks"></a>Remarks

リスト ボックスまたはコンボ ボックスから、またはリスト ボックスまたはコンボ ボックスが破棄されるときに項目が削除されると、Windows は、削除された各項目の所有者に WM_DELETEITEM メッセージを送信します。 *LParam*メッセージのパラメーターには、この構造体へのポインターが含まれています。

## <a name="requirements"></a>要件

**ヘッダー:** atldbcli.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


