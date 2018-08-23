---
title: Implements::casttounknown メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 988580a34c030c84c50adfff2741408be4b249cd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42586359"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown メソッド

基になるポインターを取得します。`IUnknown`インターフェイス。

## <a name="syntax"></a>構文

```cpp
__forceinline IUnknown* CastToUnknown();
```

## <a name="return-value"></a>戻り値

この操作は、常に成功し、返された、`IUnknown`ポインター。

## <a name="remarks"></a>Remarks

内部のヘルパー関数です。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Implements 構造体](../windows/implements-structure.md)