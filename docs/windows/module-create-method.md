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
ms.openlocfilehash: 9ae4f50e6d2d614e444766babf8e55f5c9f83932
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609545"
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