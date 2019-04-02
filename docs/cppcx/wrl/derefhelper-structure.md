---
title: DerefHelper 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 7709ae63e4d49e25aec83a069ad1ac614bfbd953
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785382"
---
# <a name="derefhelper-structure"></a>DerefHelper 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
テンプレート パラメーター。

## <a name="remarks"></a>Remarks

逆参照されたポインターを表す、`T*`テンプレート パラメーター。

**DerefHelper**など、式で使用されます。`ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`DerefType`|逆参照されるテンプレート パラメーターの識別子の`T*`します。|

## <a name="inheritance-hierarchy"></a>継承階層

`DerefHelper`

## <a name="requirements"></a>必要条件

**ヘッダー:** async.h

**名前空間:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)