---
title: Comptrref::operator InterfaceType * * 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
dev_langs:
- C++
helpviewer_keywords:
- operator InterfaceType** operator
ms.assetid: b32e3240-a4f0-4998-a55f-d4e35dc9a15a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73e1f975aa0d9a03ffb0025573ec20615825b5b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390237"
---
# <a name="comptrrefoperator-interfacetype-operator"></a>ComPtrRef::operator InterfaceType** 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
operator InterfaceType**();
```

## <a name="remarks"></a>Remarks

現在の削除**ComPtrRef**オブジェクト、ポインター-に-、- へポインターを返します、インターフェイスによって表される、 **ComPtrRef**オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ComPtrRef クラス](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)