---
description: '詳細情報: AgileActivationFactory クラス'
title: AgileActivationFactory クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::AgileActivationFactory
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
ms.openlocfilehash: 598821f3d84abd8e8ece4666a95db1d75d902125
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204629"
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

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)<br/>
[ActivationFactory クラス](activationfactory-class.md)
