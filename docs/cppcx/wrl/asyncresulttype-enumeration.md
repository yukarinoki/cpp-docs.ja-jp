---
description: '詳細については、次を参照してください: AsyncResultType 列挙型'
title: AsyncResultType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: 431c0cabf98b3636bbae02b2f05a14d11d122740
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175821"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 列挙型

メソッドによって返される結果の型を指定し `GetResults()` ます。

## <a name="syntax"></a>構文

```cpp
enum AsyncResultType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`MultipleResults`|複数の結果のセット `Start` 。状態とが呼び出される前に発生し `Close()` ます。|
|`SingleResult`|1つの結果。イベントが発生した後に表示され `Complete` ます。|

## <a name="requirements"></a>要件

**ヘッダー:** async .h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft:: WRL 名前空間](microsoft-wrl-namespace.md)
