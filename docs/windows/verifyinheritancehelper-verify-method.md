---
title: Verifyinheritancehelper::verify メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 3360082b-81ad-4191-9ec3-b4372f7207d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a337dcce390f8dc3b634018af602bc3e62e719b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396091"
---
# <a name="verifyinheritancehelperverify-method"></a>VerifyInheritanceHelper::Verify メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
static void Verify();
```

## <a name="remarks"></a>Remarks

現在のテンプレート パラメーターで指定された 2 つのインターフェイスをテストし、1 つのインターフェイスは、その他から派生されているかどうかを決定します。

1 つのインターフェイスは、その他から派生していない場合は、エラーが生成されます。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[VerifyInheritanceHelper 構造体](../windows/verifyinheritancehelper-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)