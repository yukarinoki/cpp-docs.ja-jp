---
title: _Static_assert キーワードと static_assert マクロ (C11)
description: C11 _Static_assert キーワードと C11 static_assert マクロについて説明します。
ms.date: 10/13/2020
f1_keywords:
- static_assert_c
- _Static_assert
helpviewer_keywords:
- assertions [C], _Static_assert, static_assert
ms.openlocfilehash: dbe49b1dcbb8dd4e0d9df678f4456bc605e01c3f
ms.sourcegitcommit: 651348f8cd92ab0d52f09e9225a7eb41562559db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "92060977"
---
# <a name="_static_assert-keyword-and-static_assert-macro-c11"></a>_Static_assert キーワードと static_assert マクロ (C11)

コンパイル時にアサーションをテストします。 指定された定数式が **`false`** の場合、コンパイラには、指定されたメッセージが表示され、コンパイルはエラー C2338 で失敗します。それ以外の場合、影響はありません。 C11 での新機能です。

**`_Static_assert`** は、C11 で導入されたキーワードです。
**`static_assert`** は、C11 で導入されたマクロであり、 **`_Static_assert`** キーワードにマップされます。

## <a name="syntax"></a>構文

```C
_Static_assert(constant-expression, string-literal);
static_assert(constant-expression, string-literal);
```

### <a name="parameters"></a>パラメーター

*constant-expression*\
コンパイル時に評価できる整数定数式。 式がゼロ (false) の場合、 *string-literal* パラメーターが表示され、コンパイルはエラーで失敗します。 条件がゼロ以外 (true) の場合、影響はありません。

*string-literal*\
*constant-expression* によってゼロ (false) に評価される場合に表示されるメッセージ。 このメッセージは、コンパイラの[基本文字セット](../c-language/ascii-character-set.md)を使用して作成される必要があります。 文字を[マルチバイト文字またはワイド文字](../c-language/multibyte-and-wide-characters.md)にすることはできません。

## <a name="remarks"></a>解説

コンパイル時は、ソフトウェアのアサーションが **`_Static_assert`** キーワードと **`static_assert`** マクロの両方によってテストされます。 これらは、グローバル スコープまたは関数スコープで使用できます。

これに対し、実行時は、[assert マクロ、および_assert 関数と _wassert 関数](../c-runtime-library/reference/assert-macro-assert-wassert.md)によってソフトウェアのアサーションがテストされ、ランタイム コストが発生します。

**Microsoft 固有の動作**

C では、`<assert.h>` を含まない場合、 **`static_assert`** は、Microsoft Visual C/ C++ コンパイラによって、 **`_Static_assert`** にマップするキーワードとして扱われます。 同じコードが C と C++ の両方で動作するため、 **`static_assert`** を使用することをお勧めします。

## <a name="example-of-a-compile-time-assert"></a>コンパイル時アサートの例

次の例では、 **`static_assert`** と **`_Static_assert`** を使用して、列挙に含まれる要素の数と、整数が 32 ビット幅であることを確認しています。

```C
// requires /std:c11 or higher
#include <assert.h>

enum Items
{
    A,
    B,
    C,
    LENGTH
};

int main()
{
    // _Static_assert is a C11 keyword
    _Static_assert(LENGTH == 3, "Expected Items enum to have three elements");

    // Preferred: static_assert maps to _Static_Assert and is compatible with C++
    static_assert(sizeof(int) == 4, "Expecting 32 bit integers"); 

    return 0;
}
```

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-------------|---------------------|
|**`static_assert`**|\<assert.h>|

## <a name="see-also"></a>関連項目

[_STATIC_ASSERT マクロ](../c-runtime-library/reference/static-assert-macro.md)\
[assert マクロおよび _assert 関数と _wassert 関数 ](../c-runtime-library/reference/assert-macro-assert-wassert.md)
[/std (言語標準バージョンを指定します)](../build/reference/std-specify-language-standard-version.md)