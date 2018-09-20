---
title: AgileActivationFactory クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::AgileActivationFactory
dev_langs:
- C++
ms.assetid: fab98f32-bb93-4c0f-badb-49fbddb194b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d6b2ff0b9b23e8e3a540cf7bbcd6ae55ebab13d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435377"
---
# <a name="agileactivationfactory-class"></a>AgileActivationFactory クラス

実装するアパートメント対応のアクティベーション ファクトリを表す[FtmBase](../windows/ftmbase-class.md)します。
  
## <a name="syntax"></a>構文
  
```cpp
template <
   typename I0 = Details::Nil,
   typename I1 = Details::Nil,
   typename I2 = Details::Nil,
FactoryCacheFlags cacheFlagValue = FactoryCacheDefault>
class AgileActivationFactory :
   public ActivationFactory<Implements<FtmBase, I0>, I1, I2, cacheFlagValue>{};
```
  
## <a name="requirements"></a>要件

**ヘッダー:** module.h
  
**名前空間:** Microsoft::WRL
  
## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)<br/>
[ActivationFactory クラス](../windows/activationfactory-class.md)