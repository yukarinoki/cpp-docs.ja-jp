---
title: goto ステートメントとラベル付きステートメント (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf56a409f9a76cdf401323d1425ee28fc6cf286b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386415"
---
# <a name="goto-and-labeled-statements-c"></a>goto ステートメントとラベル付きステートメント (C)
`goto` ステートメントは、特定のラベルに制御を移します。 この特定のラベルは、同じ関数内に存在する必要があり、同じ関数内の 1 つのステートメントの前にのみ指定できます。  
  
## <a name="syntax"></a>構文  
 *statement*:  
 *labeled-statement*  
  
 *jump-statement*  
  
 *jump-statement*:  
 **goto**  *identifier*  **;**  
  
 *labeled-statement*:  
 *identifier*  **:**  *statement*  
  
 ステートメント ラベルは `goto` ステートメントに対してのみ意味を持ちます。他のコンテキストでは、ラベル付きステートメントはラベルに関係なく実行されます。  
  
 *jump-statement* は同じ関数に存在する必要があり、同じ関数の特定のステートメントの前にのみ指定できます。 `goto` に続く *identifier* の名前のセットには独自の名前空間があるため、名前が他の識別子に干渉することはありません。 ラベルは再宣言できません。 詳細については、「[名前空間](../c-language/name-spaces.md)」を参照してください。  
  
 可能な限り、`goto` より **break**、**continue**、および `return` ステートメントを使用することをお勧めします。 **break** ステートメントは、ループの 1 つのレベルから抜けるだけであるため、`goto` は、深い入れ子になっているループ内からループを終了する場合に必要になることがあります。  
  
 `goto` ステートメントの例を次に示します。  
  
```  
// goto.c  
#include <stdio.h>  
  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 3; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 5 )  
                goto stop;  
        }  
    }  
  
    /* This message does not print: */  
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop: printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
 この例で `goto` ステートメントは、`i` が 5 に等しい場合に、`stop` というラベルの位置に制御を移します。  
  
## <a name="see-also"></a>参照  
 [ステートメント](../c-language/statements-c.md)