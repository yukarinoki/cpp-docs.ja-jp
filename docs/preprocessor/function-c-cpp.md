---
description: pragmaMicrosoft C/c + + での function ディレクティブの詳細について説明します。
title: プロシージャ pragma
ms.date: 01/22/2021
f1_keywords:
- function_CPP
- vc-pragma.function
helpviewer_keywords:
- function pragma
- pragma, function
no-loc:
- pragma
ms.openlocfilehash: 3d4b1e2f50cd118e613235271428588ac585affc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712831"
---
# <a name="function-no-locpragma"></a>`function` pragma

を pragma インライン展開するのではなく、の引数リストで指定された関数の呼び出しを生成するようコンパイラに指示します。

## <a name="syntax"></a>構文

> **`#pragma function(`***function1* [ **`,`** *function2* ...]**`)`**

## <a name="remarks"></a>解説

組み込み関数は、通常、関数呼び出しとしてではなく、インラインコードとして生成されます。 [ `intrinsic` pragma](intrinsic.md)またはコンパイラオプションを使用して、組み込み関数を生成するようにコンパイラに指示した場合は [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) 、を使用して **`function`** pragma 明示的に関数呼び出しを強制することができます。 **`function`** pragma が表示されると、指定された組み込み関数を含む最初の関数定義で有効になります。 効果は、ソースファイルの末尾、または同じ組み込み関数を指定するの外観に続き `intrinsic` pragma ます。 は、 **`function`** pragma 関数の外部でのみ、グローバルレベルで使用できます。

組み込みフォームを持つ関数の一覧については[ `intrinsic` pragma ](intrinsic.md)、「」を参照してください。

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

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
