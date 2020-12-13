---
description: '詳細については、次を参照してください: RuntimeClassType 列挙型'
title: RuntimeClassType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 10055d79148124e886c4da50e40ffdb7d3d0fec0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135279"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型

サポートされている [RuntimeClass](runtimeclass-class.md) インスタンスの種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`ClassicCom`|従来の COM ランタイムクラス。|
|`Delegate`|これは、`ClassicCom` に相当します。|
|`InhibitFtmBase`|`FtmBase` `__WRL_CONFIGURATION_LEGACY__` が定義されていないときのサポートを無効にします。|
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|
|`WinRt`|Windows ランタイムクラス。|
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
