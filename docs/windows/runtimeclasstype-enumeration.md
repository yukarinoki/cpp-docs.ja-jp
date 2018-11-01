---
title: RuntimeClassType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
ms.openlocfilehash: 62a82d5fab9fd22e23a5244d4fda3b7f5202304c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626812"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 列挙型

型を指定[RuntimeClass](../windows/runtimeclass-class.md)サポートされているインスタンス。

## <a name="syntax"></a>構文

```cpp
enum RuntimeClassType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ClassicCom`|クラシック COM ランタイム クラスです。|
|`Delegate`|これは、`ClassicCom` に相当します。|
|`InhibitFtmBase`|無効にします`FtmBase`する際にサポート`__WRL_CONFIGURATION_LEGACY__`が定義されていません。|
|`InhibitWeakReference`|弱い参照のサポートを無効にします。|
|`WinRt`|Windows ランタイム クラスです。|
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|

## <a name="requirements"></a>必要条件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)