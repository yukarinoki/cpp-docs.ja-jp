---
title: Interfacetraits::verify メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: 46edd67f-7952-4552-a157-55e823f616c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e1950d6e9d5195ece315863b664b42411231184d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415383"
---
# <a name="interfacetraitsverify-method"></a>InterfaceTraits::Verify メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
__forceinline static void Verify();
```

## <a name="remarks"></a>Remarks

検証が行われます`Base`は正しく派生します。

詳細については`Base`を参照してください、**パブリック Typedef**セクション[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[InterfaceTraits 構造体](../windows/interfacetraits-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)