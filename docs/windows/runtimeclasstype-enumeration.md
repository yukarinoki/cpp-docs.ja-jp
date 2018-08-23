---
title: RuntimeClassType 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3358455755ec4c00ebea85fc13fe0022c7b6697
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595455"
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

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)