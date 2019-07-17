---
title: '&lt;cstdarg&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdarg>
helpviewer_keywords:
- cstdarg header
ms.assetid: 639b4ef7-8408-4640-9343-41631f0ab663
ms.openlocfilehash: f8d2d3b886cfa46905e8f17f1e13b51881b80191
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244482"
---
# <a name="ltcstdarggt"></a>&lt;cstdarg&gt;

標準 C ライブラリ ヘッダーが含まれています\<stdarg.h > を関連する名前を追加し、`std`名前空間。 外部リンケージを使用して、標準 C ライブラリ ヘッダーで宣言された名前を宣言することにより、このヘッダーを含む、`std`名前空間。

## <a name="syntax"></a>構文

```cpp
#include <cstdarg>
```

## <a name="namespace-and-macros"></a>Namespace とマクロ

```cpp
namespace std {
    using va_list = see below;
}

#define va_arg(V, P)
#define va_copy(VDST, VSRC)
#define va_end(V)
#define va_start(V, P)
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
