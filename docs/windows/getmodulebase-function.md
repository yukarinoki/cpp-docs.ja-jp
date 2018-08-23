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
ms.openlocfilehash: 403330097f1428ee0d7650f5931aef1621f61b11
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612602"
---
# <a name="getmodulebase-function"></a>GetModuleBase 関数
取得、 [ModuleBase](../windows/modulebase-class.md)の参照カウントをインクリメントおよびデクリメントするため、ポインター、 [RuntimeClass](../windows/runtimeclass-class.md)オブジェクト。
  
## <a name="syntax"></a>構文
  
```cpp
inline Details::ModuleBase* GetModuleBase() throw()  
```
  
## <a name="return-value"></a>戻り値
 ポインターを`ModuleBase`オブジェクト。
  
## <a name="remarks"></a>Remarks
 この関数は、インクリメントおよびデクリメントを内部的に使用されますオブジェクト参照をカウントします。
  
 この関数を使用して、呼び出すことによって参照カウントを制御することができます[modulebase::incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md)と[modulebase::decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md)します。
  
## <a name="requirements"></a>要件
 **ヘッダー:** implements.h
  
 **名前空間:** Microsoft::WRL
  
## <a name="see-also"></a>関連項目
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)