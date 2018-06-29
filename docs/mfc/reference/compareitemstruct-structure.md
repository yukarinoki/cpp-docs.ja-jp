---
title: COMPAREITEMSTRUCT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a54b4f4749e7865d793559a9cb5f475c1d57898
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078259"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 構造体
`COMPAREITEMSTRUCT`構造が、識別子と、並べ替えられたオーナー描画リスト ボックスまたはコンボ ボックスの 2 つの項目のアプリケーションによって提供されるデータを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *CtlType*  
 **ODT_LISTBOX** (オーナー描画リスト ボックスを指定する) または**ODT_COMBOBOX** (オーナー描画コンボ ボックスを指定する)。  
  
 *CtlID*  
 リスト ボックスまたはコンボ ボックスのコントロール ID。  
  
 *hwndItem*  
 コントロールのウィンドウ ハンドル。  
  
 *itemID1*  
 リスト ボックスまたはコンボ ボックスの比較対象となる最初の項目のインデックス。  
  
 *itemData1*  
 比較対象となる最初の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。  
  
 *itemID2*  
 リスト ボックスまたはコンボ ボックスの比較対象となる 2 番目の項目のインデックス。  
  
 *itemData2*  
 比較対象となる 2 番目の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。  
  
## <a name="remarks"></a>Remarks  
 ときに、アプリケーションがオーナー描画リスト ボックスに新しい項目を追加またはで作成されたコンボ ボックス、 **CBS_SORT**または**LBS_SORT**スタイル、Windows 所有者 WM_COMPAREITEM がメッセージを送信します。 *LParam* 、メッセージのパラメーターにはへの long ポインターが含まれています、`COMPAREITEMSTRUCT`構造体。 メッセージを受信したときは、所有者は、2 つの項目を比較し、どの項目が、他のより前に来ることを示す値を返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

