---
title: Eventtargetarray::eventtargetarray コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 831c9a524f8120c855382d198a5f53ac312cada6
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569789"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *hr*  
 このコンス トラクター操作後にパラメーター *hr*配列の割り当てが成功または失敗するかどうかを示します。 次の表に、可能な値*hr*します。  
  
 S_OK  
 操作が成功しました。  
  
 E_OUTOFMEMORY  
 配列にメモリを割り当てできませんでした。  
  
 S_FALSE  
 パラメーター*項目*が 0 未満です。  
  
 *項目*  
 割り当てる配列要素の数。  
  
## <a name="remarks"></a>Remarks  
 新しいインスタンスを初期化、 **EventTargetArray**クラス。  
  
 **EventTargetArray**配列内のイベント ハンドラーを保持するために使用する`EventSource`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [EventTargetArray クラス](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)