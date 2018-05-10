---
title: 関数 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs:
- C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e24dac191e05cc3b47192cb6ec7fb0fc48dd447
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="function-cc"></a>function (C/C++)
このプラグマの引数リストで指定された関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>コメント  
 使用する場合、**組み込み**プラグマ (または/Oi) コンパイラに通知します (組み込み関数は、関数呼び出しとしてではなく、インライン コードとして生成されます) の組み込み関数を生成する、使用することができます、**関数**プラグマ関数呼び出しを明示的に強制します。 コンパイラが function プラグマを検出した後、組み込み関数を含む最初の関数定義に達した時点でそのプラグマが有効になります。 ソース ファイルの末尾にまたはの外観に効果が引き続き、**組み込み**プラグマ同じ組み込み関数を指定します。 **関数**プラグマは関数の外側でのみ使用できます: グローバル レベルでします。  
  
 組み込み形式を持つ関数の一覧は、次を参照してください。 [#pragma intrinsic](../preprocessor/intrinsic.md)です。  
  
## <a name="example"></a>例  
  
```  
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