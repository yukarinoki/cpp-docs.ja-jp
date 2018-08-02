---
title: Criticalsection::trylock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1b9d238d4f5475475e5dc367aae196937630a0e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465423"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock メソッド
ブロックすることがなく、クリティカル セクションを入力しようとします。 呼び出しが成功した場合、呼び出し元のスレッドはクリティカル セクションの所有権を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *cs*  
 ユーザー指定のクリティカル セクション オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 クリティカル セクションが正しく入力された場合は 0 以外の値または現在のスレッドはクリティカル セクションを既に所有しています。 別のスレッドがクリティカル セクション既に所有している場合は 0 します。  
  
## <a name="remarks"></a>Remarks  
 最初の**TryLock**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目の**TryLock**関数、ユーザー指定のクリティカル セクションに影響を与えます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [CriticalSection クラス](../windows/criticalsection-class.md)