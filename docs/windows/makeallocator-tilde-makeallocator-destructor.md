---
title: 'MakeAllocator:: ~ MakeAllocator デストラクター |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- ~MakeAllocator, destructor
ms.assetid: f1299c5f-cc6b-4d4e-85d4-aee1be0e2b0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ba40aa98321956f19de30f5f4002cb788ff446e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46371993"
---
# <a name="makeallocatormakeallocator-destructor"></a>MakeAllocator::~MakeAllocator デストラクター

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
~MakeAllocator();
```

## <a name="remarks"></a>Remarks

現在のインスタンスの初期化を解除、 **MakeAllocator**クラス。

このデストラクターは必要な場合も、基になる割り当てられたメモリを削除します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[MakeAllocator クラス](../windows/makeallocator-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)