---
title: InspectableClass マクロ
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: 755a8f58ffc290d73d6060b0b0924905ecbf6028
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213877"
---
# <a name="inspectableclass-macro"></a>InspectableClass マクロ

ランタイム クラス名と信頼レベルを設定します。

## <a name="syntax"></a>構文

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>パラメーター

*runtimeClassName*<br/>
ランタイム クラス名のテキスト形式の完全な名前です。

*trustLevel*<br/>
[TrustLevel](/windows/win32/api/inspectable/ne-inspectable-trustlevel)列挙値のいずれか。

## <a name="remarks"></a>解説

**InspectableClass**マクロは Windows ランタイム型でのみ使用できます。

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[RuntimeClass クラス](runtimeclass-class.md)
