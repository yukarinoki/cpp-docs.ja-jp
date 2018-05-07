---
title: DELETEITEMSTRUCT 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 2f56a09742276c7fcb1bd66ff1a36b1d17cdf882
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT 構造体
`DELETEITEMSTRUCT`構造が削除されたオーナー描画リスト ボックスまたはコンボ ボックス項目について説明します。  
  
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
 `CtlType`  
 指定**ODT_LISTBOX** (オーナー描画リスト ボックス、) または**ODT_COMBOBOX** (オーナー描画コンボ ボックス、)。  
  
 `CtlID`  
 リスト ボックスまたはコンボ ボックスの識別子を指定します。  
  
 `itemID`  
 リスト ボックスまたはコンボ ボックスの削除された項目のインデックスを指定します。  
  
 `hwndItem`  
 コントロールを識別します。  
  
 `itemData`  
 アイテムのアプリケーション定義のデータを指定します。 コントロールにこの値は、 **lParam**リスト ボックスまたはコンボ ボックスに、項目を追加、メッセージのパラメーターです。  
  
## <a name="remarks"></a>コメント  
 リスト ボックスまたはコンボ ボックスから、またはリスト ボックスまたはコンボ ボックスが破棄されるときに項目が削除されると、Windows の送信、`WM_DELETEITEM`削除される各項目の所有者へのメッセージ。 **LParam**メッセージのパラメーターには、この構造体へのポインターが含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


