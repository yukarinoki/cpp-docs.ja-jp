---
title: GetModuleBase 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afa76ad23c509689dd693bb0f3e13dbb7adb4d54
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075451"
---
# <a name="getmodulebase-function"></a>GetModuleBase 関数
取得、 [ModuleBase](../windows/modulebase-class.md)の参照カウントをインクリメントおよびデクリメントするため、ポインター、 [RuntimeClass](../windows/runtimeclass-class.md)オブジェクト。

## <a name="syntax"></a>構文

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>戻り値

`ModuleBase` オブジェクトへのポインター。

## <a name="remarks"></a>Remarks

この関数は、インクリメントおよびデクリメントを内部的に使用されますオブジェクト参照をカウントします。

この関数を使用して、呼び出すことによって参照カウントを制御することができます[modulebase::incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md)と[modulebase::decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md)します。

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)