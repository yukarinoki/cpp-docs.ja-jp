---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 14dda03e835ec411013b2d827bd1ccaa77f8982e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245015"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

標準 C ライブラリ ヘッダーが含まれています\<assert.h > を関連する名前を追加し、`std`名前空間。 外部リンケージを使用して、標準 C ライブラリ ヘッダーで宣言された名前を宣言することにより、このヘッダーを含む、`std`名前空間。

> [!NOTE]
> \<assert.h > が定義されていない、`static_assert`マクロ。

## <a name="syntax"></a>構文

```cpp
#include <cassert>
```

## <a name="macros"></a>[マクロ]

```cpp
#define assert(E)
```

### <a name="remarks"></a>Remarks

`assert(E)` 定数、NDEBUG が定義されている場合のみ、`assert`定義または再定義された、最後または*E*に変換に評価されるブール**true**。

## <a name="see-also"></a>関連項目

[assert マクロ、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
