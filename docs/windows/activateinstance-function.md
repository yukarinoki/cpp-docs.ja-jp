---
title: ActivateInstance 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0bf945dd8225ca3c153d7f497ded6b83ebd022d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855576"
---
# <a name="activateinstance-function"></a>ActivateInstance 関数
登録し、指定したクラス ID で定義されている、指定した型のインスタンスを取得します  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 アクティブ化する型。  
  
 `activatableClassId`  
 パラメーターを定義するクラスの ID の名前`T`です。  
  
 `instance`  
 この操作の完了時のインスタンスへの参照を`T`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、エラーのエラーの原因を示す hresult 値。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** windows::foundation  
  
## <a name="see-also"></a>関連項目  
 [Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)