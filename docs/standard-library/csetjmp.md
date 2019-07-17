---
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: 3eba0b4521c0abf414de1416f02039a67c896644
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244516"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

標準 C ライブラリ ヘッダー \<setjmp.h> をインクルードし、関連する名前を `std` 名前空間に追加します。

## <a name="syntax"></a>構文

```cpp
#include <csetjmp>

using jmp_buf = see below;
```

## <a name="functions"></a>関数

```cpp
[[noreturn]] void longjmp(jmp_buf env, int val);
```

## <a name="macros"></a>[マクロ]

```cpp
#define setjmp(env)
```

## <a name="remarks"></a>Remarks

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
