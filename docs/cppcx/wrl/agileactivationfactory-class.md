---
title: AgileActivationFactory クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::AgileActivationFactory
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
ms.openlocfilehash: d4f437f87861293cb6048ed6acb05428c466b3f3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214202"
---
# <a name="agileactivationfactory-class"></a>AgileActivationFactory クラス

[Ftmbase](ftmbase-class.md)を実装するアパートメントに対応するアクティベーションファクトリを表します。

## <a name="syntax"></a>構文

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil,
    FactoryCacheFlags cacheFlagValue = FactoryCacheDefault
>
class AgileActivationFactory :
    public ActivationFactory<
        Implements<FtmBase, I0>,
        I1,
        I2,
        cacheFlagValue
    >;
```

## <a name="requirements"></a>必要条件

**ヘッダー:** resource.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[ActivationFactory クラス](activationfactory-class.md)
