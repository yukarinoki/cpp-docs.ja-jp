---
title: AsyncResultType 列挙型
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: b8a2a9ec803fba1be0012fcb58bf3b42e78f9071
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214163"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 列挙型

`GetResults()` メソッドによって返される結果の種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum AsyncResultType;
```

## <a name="members"></a>メンバー

### <a name="values"></a>値

|Name|説明|
|----------|-----------------|
|`MultipleResults`|複数の結果のセット。 `Start` の状態と `Close()` が呼び出される前に徐々に表示されます。|
|`SingleResult`|1つの結果。 `Complete` イベントが発生した後に表示されます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** async .h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
