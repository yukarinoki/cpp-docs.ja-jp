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
ms.openlocfilehash: 5c844ad428143c82e8214eab74262b326bf2c9a4
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123241"
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
 *CtlType*  
 ODT_LISTBOX (オーナー描画リスト ボックス、) または ODT_COMBOBOX (オーナー描画コンボ ボックス、) を指定します。  
  
 *CtlID*  
 リスト ボックスまたはコンボ ボックスの識別子を指定します。  
  
 *itemID*  
 リスト ボックスまたはコンボ ボックスの削除された項目のインデックスを指定します。  
  
 *hwndItem*  
 コントロールを識別します。  
  
 *取得*  
 アイテムのアプリケーション定義のデータを指定します。 コントロールにこの値は、 *lParam*リスト ボックスまたはコンボ ボックスに、項目を追加、メッセージのパラメーターです。  
  
## <a name="remarks"></a>Remarks  
 リスト ボックスまたはコンボ ボックスから、またはリスト ボックスまたはコンボ ボックスが破棄されるときに項目が削除されると、Windows は、削除される各項目の所有者を WM_DELETEITEM メッセージを送信します。 *LParam*メッセージのパラメーターには、この構造体へのポインターが含まれています。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


