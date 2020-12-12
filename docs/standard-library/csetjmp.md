---
description: '詳細情報: &lt; csetjmp&gt;'
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: ebd3acefbdf96c8dd2b0cba569e7cd2ffc128d31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324775"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

標準 C ライブラリヘッダーをインクルード \<setjmp.h> し、関連する名前を名前空間に追加し `std` ます。

## <a name="syntax"></a>構文

```cpp
#include <csetjmp>

using jmp_buf = see below;
```

## <a name="functions"></a>関数

```cpp
[[noreturn]] void longjmp(jmp_buf env, int val);
```

## <a name="macros"></a>マクロ

```cpp
#define setjmp(env)
```

## <a name="remarks"></a>解説

このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
