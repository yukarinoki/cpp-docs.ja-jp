---
title: Comptrref::operator * 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e2af57b698558a33115cfcfc20ebc7136e72dc6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400739"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator* 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
InterfaceType* operator *();
```

## <a name="return-value"></a>戻り値

現在によって表されるインターフェイスへのポインター **ComPtrRef**オブジェクト。

## <a name="remarks"></a>Remarks

現在によって表されるインターフェイスへのポインターを取得します。 **ComPtrRef**オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ComPtrRef クラス](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)