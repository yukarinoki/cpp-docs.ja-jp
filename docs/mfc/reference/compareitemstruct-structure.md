---
title: COMPAREITEMSTRUCT 構造体 |Microsoft Docs
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
ms.openlocfilehash: 6c42f356cb323bb7690b6c39b1fc7bd9ce0485f3
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850590"
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 構造体
`COMPAREITEMSTRUCT`構造体は、識別子と並べ替えられた、オーナー描画リスト ボックスまたはコンボ ボックスの 2 つの項目のアプリケーションによって提供されるデータを提供します。  
  
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
 (これは、オーナー描画リスト ボックスを指定します) ODT_LISTBOX または ODT_COMBOBOX (元のオーナー描画のコンボ ボックスを指定)。  
  
 *CtlID*  
 リスト ボックスまたはコンボ ボックス コントロールの ID。  
  
 *hwndItem*  
 コントロールのウィンドウ ハンドル。  
  
 *itemID1*  
 リスト ボックスまたはコンボ ボックスの比較対象の最初の項目のインデックス。  
  
 *itemData1*  
 比較対象となる最初の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。  
  
 *itemID2*  
 リスト ボックスまたはコンボ ボックスの比較対象となる 2 番目の項目のインデックス。  
  
 *itemData2*  
 比較対象となる 2 番目の項目のアプリケーションによって提供されるデータ。 この値は、コンボ ボックスまたはリスト ボックスに、項目を追加する呼び出しに渡されました。  
  
## <a name="remarks"></a>Remarks  
 アプリケーションでは、オーナー描画リスト ボックスまたは CBS_SORT または LBS_SORT スタイルで作成したコンボ ボックスに新しい項目を追加するたびに Windows は WM_COMPAREITEM メッセージ、所有者を送信します。 *LParam*メッセージのパラメーターにはへの long ポインターが含まれています、`COMPAREITEMSTRUCT`構造体。 メッセージを受信するとは、所有者は、2 つの項目を比較し、前に、その他のどの項目が並べ替えを示す値を返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

