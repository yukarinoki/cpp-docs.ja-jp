---
title: HANDLENullTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLENullTraits structure
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a49a1a1ac4495c7697fc041f8fcf217850f09d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609425"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits 構造体

初期化されていないハンドルの一般的な特性を定義します。

## <a name="syntax"></a>構文

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`Type`|ハンドルのシノニムです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[HANDLENullTraits::Close メソッド](../windows/handlenulltraits-close-method.md)|指定したハンドルを閉じます。|
|[HANDLENullTraits::GetInvalidValue メソッド](../windows/handlenulltraits-getinvalidvalue-method.md)|無効なハンドルを表します。|

## <a name="inheritance-hierarchy"></a>継承階層

`HANDLENullTraits`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)