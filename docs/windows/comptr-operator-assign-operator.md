---
title: Comptr::operator = 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f4066db37de8a993802970784f09141352fef028
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871202"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= 演算子
値を現在の ComPtr に割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 クラスです。  
  
 `other`  
 もう 1 つの ComPtr、または型へのポインター、参照、または右辺値参照。  
  
## <a name="return-value"></a>戻り値  
 現在の ComPtr への参照。  
  
## <a name="remarks"></a>コメント  
 この演算子の最初のバージョンでは、現在の ComPtr に空の値を割り当てます。  
  
 2 番目のバージョンでは、割り当てのインターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 3 番目のバージョンでは、割り当てのインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 4 番目のバージョンでは、割り当ての値のインターフェイス ポインターが現在の ComPtr インターフェイス ポインターと同じでない場合、2 番目のインターフェイス ポインターが現在の ComPtr に割り当てられます。  
  
 5 番目のバージョンがコピー演算子です。ComPtr への参照は、現在の ComPtr に割り当てられます。  
  
 6 番目のバージョンがコピー演算子を使用する移動セマンティクスです。ComPtr キャストし、現在の ComPtr に代入して、任意の型が静的な場合に右辺値参照。  
  
 7 番目のバージョンがコピー演算子を使用する移動セマンティクスです。型の ComPtr への右辺値参照`U`静的キャストし、現在の ComPtr に割り当てられています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)