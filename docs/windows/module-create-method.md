---
title: Module::create メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99ede64c239909956f1f767db34a2a6a14c02314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="modulecreate-method"></a>Module::Create メソッド
モジュールのインスタンスを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW static Module& Create();  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<typename T>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 モジュールの種類。  
  
 `callback`  
 モジュールの最後のインスタンスのオブジェクトがリリースされたときに呼び出されます。  
  
 `object`  
 `object`と`method`パラメーターの組み合わせで使用されます。 場合に、ポイント最後のインスタンス オブジェクト、モジュール内の最後のインスタンス オブジェクトを解放します。  
  
 `method`  
 `object`と`method`パラメーターの組み合わせで使用されます。 モジュールの最後のインスタンス オブジェクトが離されると、最後のインスタンス オブジェクトのメソッドを指します。  
  
## <a name="return-value"></a>戻り値  
 モジュールへの参照。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
[Module クラス](../windows/module-class.md)

 