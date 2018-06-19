---
title: Criticalsection::lock メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c873494a702802b8ead3dab9cac28557664f618
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871326"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock メソッド
指定されたクリティカル セクション オブジェクトの所有権を待機します。 この関数は、呼び出し元のスレッドには、所有権が付与されるを返します。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cs`  
 クリティカル セクションのユーザーが指定したオブジェクトです。  
  
## <a name="return-value"></a>戻り値  
 現在の重要なセクションのロック解除に使用できるロック オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初の**ロック**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目**ロック**関数、ユーザー指定のクリティカル セクションに影響します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [CriticalSection クラス](../windows/criticalsection-class.md)