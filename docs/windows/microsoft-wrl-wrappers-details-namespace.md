---
title: Microsoft::WRL::Wrappers::Details 名前空間
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
ms.openlocfilehash: 09f3fd1011b05e9aee9816663cb5bd1d9e0081e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431877"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Microsoft::WRL::Wrappers::Details 名前空間

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|名前|説明|
|----------|-----------------|
|[SyncLockT クラス](../windows/synclockt-class.md)|排他的に使用できる型を表すか、リソースの所有権を共有します。|
|[SyncLockWithStatusT クラス](../windows/synclockwithstatust-class.md)|排他的に使用できる型を表すか、リソースの所有権を共有します。|

### <a name="methods"></a>メソッド

|名前|説明|
|----------|-----------------|
|[CompareStringOrdinal メソッド](../windows/comparestringordinal-method.md)|指定した 2 つ比較`HSTRING`オブジェクトし、並べ替え順序においてそれらの相対位置を示す整数を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)