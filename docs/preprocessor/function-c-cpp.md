---
title: function (C/C++)
ms.date: 11/04/2016
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
ms.openlocfilehash: c57ff2053b3c1fd52474c7eb0dd598641632f789
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027260"
---
# <a name="function-cc"></a>function (C/C++)
このプラグマの引数リストで指定された関数を呼び出します。

## <a name="syntax"></a>構文

```
#pragma function( function1 [, function2, ...] )
```

## <a name="remarks"></a>Remarks

使用する場合、`intrinsic`プラグマ (または/Oi) 使用することができます (組み込み関数は、関数呼び出しとしてではなく、インライン コードとして生成されます) の組み込み関数を生成するコンパイラを指示する、**関数**プラグマを明示的に適用します。関数呼び出し。 コンパイラが function プラグマを検出した後、組み込み関数を含む最初の関数定義に達した時点でそのプラグマが有効になります。 ソース ファイルの末尾に、またはの外観に影響が引き続き、`intrinsic`プラグマと同じ組み込み関数を指定します。 **関数**プラグマは関数の外側でのみ使用できます: グローバル レベル。

組み込み形式を持つ関数の一覧は、次を参照してください。 [#pragma intrinsic](../preprocessor/intrinsic.md)します。

## <a name="example"></a>例

```cpp
// pragma_directive_function.cpp
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// use intrinsic forms of memset and strlen
#pragma intrinsic(memset, strlen)

// Find first word break in string, and set remaining
// chars in string to specified char value.
char *set_str_after_word(char *string, char ch) {
   int i;
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */

   for(i = 0; i < len; i++) {
      if (isspace(*(string + i)))
         break;
   }

   for(; i < len; i++)
      *(string + i) = ch;

   return string;
}

// do not use strlen intrinsic
#pragma function(strlen)

// Set all chars in string to specified char value.
char *set_str(char *string, char ch) {
   // Uses intrinsic for memset, but calls strlen library function
   return (char *) memset(string, ch, strlen(string));
}

int main() {
   char *str = (char *) malloc(20 * sizeof(char));

   strcpy_s(str, sizeof("Now is the time"), "Now is the time");
   printf("str is '%s'\n", set_str_after_word(str, '*'));
   printf("str is '%s'\n", set_str(str, '!'));
}
```

```Output
str is 'Now************'
str is '!!!!!!!!!!!!!!!'
```

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)