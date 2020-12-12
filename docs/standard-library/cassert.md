---
description: '詳細情報: &lt; cassert&gt;'
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: e2b515fe492e6847c4d0cc5841dc43a2d879dd99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325357"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

C 標準ライブラリヘッダーをインクルード \<assert.h> し、関連する名前を名前空間に追加し `std` ます。 このヘッダーをインクルードすると、C 標準ライブラリヘッダーの外部リンケージを使用して宣言された名前が、名前空間で宣言され `std` ます。

> [!NOTE]
> \<assert.h> マクロは定義されていません **`static_assert`** 。

## <a name="syntax"></a>構文

```cpp
#include <cassert>
```

## <a name="macros"></a>マクロ

```cpp
#define assert(E)
```

### <a name="remarks"></a>解説

`assert(E)`は定数です。が最後に定義または再定義された場所で NDEBUG が定義されている場合、またはブール型に変換された場合、は `assert` に評価され **`true`** ます。

## <a name="see-also"></a>関連項目

[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
