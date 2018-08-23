---
title: Criticalsectiontraits::getinvalidvalue メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4a23445cc9df0553a40d4f78a7ce3095a343d5d0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599237"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue メソッド

専門、 **CriticalSection**テンプレート、テンプレートが常に有効なされないようにします。

## <a name="syntax"></a>構文

```cpp
inline static Type GetInvalidValue();
```

## <a name="return-value"></a>戻り値

常に無効な重要なセクションにポインターを返します。

## <a name="remarks"></a>Remarks

`Type`として修飾子が定義されている`typedef CRITICAL_SECTION* Type;`します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)