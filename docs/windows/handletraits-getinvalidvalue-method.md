---
title: Handletraits::getinvalidvalue メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: e95d2cc1-e70f-463f-8ff0-183cdeac1138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 82616b0fc8cda44ea501b87f6ac1c6e0eddbfb57
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609363"
---
# <a name="handletraitsgetinvalidvalue-method"></a>HANDLETraits::GetInvalidValue メソッド

無効なハンドルを表します。

## <a name="syntax"></a>構文

```cpp
inline static HANDLE GetInvalidValue();
```

## <a name="return-value"></a>戻り値

INVALID_HANDLE_VALUE を常に返します。 (INVALID_HANDLE_VALUE は Windows によって定義されます)。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[HANDLETraits 構造体](../windows/handletraits-structure.md)