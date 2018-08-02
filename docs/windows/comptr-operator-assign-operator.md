---
title: Comptr::operator = 演算子 |Microsoft Docs
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
ms.openlocfilehash: fac3a845ea7c512f5a7ccffdabdf67ce26029ff8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466164"
---
# <a name="comptroperator-operator"></a>ComPtr::operator= 演算子
現在の値を代入**ComPtr**します。  
  
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
 *U*  
 クラス。  
  
 *other*  
 ポインター、参照、または右辺値参照型または別に**ComPtr**します。  
  
## <a name="return-value"></a>戻り値  
 現在への参照を**ComPtr**します。  
  
## <a name="remarks"></a>Remarks  
 この演算子の最初のバージョンは現在空の値を割り当てます**ComPtr**します。  
  
 2 番目のバージョンでは、割り当てのインターフェイス ポインターでない現在のと同じ場合**ComPtr**インターフェイス ポインターの場合は、2 番目のインターフェイス ポインターが現在割り当てられている**ComPtr**します。  
  
 現在の 3 番目のバージョンでは、割り当てのインターフェイス ポインターが割り当てられている**ComPtr**します。  
  
 4 番目のバージョンでは、割り当ての値のインターフェイス ポインターでない現在のと同じ場合**ComPtr**インターフェイス ポインターの場合は、2 番目のインターフェイス ポインターが現在割り当てられている**ComPtr**します。  
  
 5 番目のバージョンがコピー演算子です。参照を**ComPtr**に現在割り当てられている**ComPtr**します。  
  
 6 番目のバージョンを使用するコピー操作は、移動セマンティクスです。右辺値参照を**ComPtr**キャストし、現在割り当てられている、任意の型が静的な場合**ComPtr**します。  
  
 7 番目のバージョンを使用するコピー操作は、移動セマンティクスです。右辺値参照を**ComPtr**型の*U*は静的キャストしとに現在割り当てられている**ComPtr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)