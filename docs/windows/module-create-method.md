---
title: Module::create メソッド |Microsoft Docs
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
ms.openlocfilehash: 1b3f865addd83bec64250807285947ea1c92e59f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016614"
---
# <a name="modulecreate-method"></a>Module::Create メソッド
モジュールのインスタンスを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
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
  
### <a name="parameters"></a>パラメーター  
 *T*  
 モジュールの種類。  
  
 *コールバック*  
 モジュールの最後のインスタンス オブジェクトを解放するときに呼び出されます。  
  
 *object*  
 *オブジェクト*と*メソッド*パラメーターの組み合わせで使用されます。 ポイント最後のインスタンス オブジェクト、モジュールの最後のインスタンスのオブジェクトがリリースされたときにします。  
  
 *method*  
 *オブジェクト*と*メソッド*パラメーターの組み合わせで使用されます。 モジュールの最後のインスタンスのオブジェクトがリリースされたときに、最後のインスタンス オブジェクトのメソッドを指します。  
  
## <a name="return-value"></a>戻り値  
 モジュールへの参照。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
[Module クラス](../windows/module-class.md)