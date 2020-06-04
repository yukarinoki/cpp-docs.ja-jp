---
title: RuntimeClassType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 53f0172968c28762bb1305e274bbd47494cdaf4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213578"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型

サポートされている[RuntimeClass](runtimeclass-class.md)インスタンスの種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`ClassicCom`|従来の COM ランタイムクラス。|
|`Delegate`|`ClassicCom` と同等です。|
|`InhibitFtmBase`|`__WRL_CONFIGURATION_LEGACY__` が定義されていない場合に `FtmBase` サポートを無効にします。|
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|
|`WinRt`|Windows ランタイムクラス。|
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
