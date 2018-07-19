---
title: goto ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7676f38e52734fa2f0ce8ecbc9b268be1939f6dc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953396"
---
# <a name="goto-statement-c"></a>goto ステートメント (C++)
**Goto**ステートメントは無条件で指定した識別子によってラベル付けステートメントに制御を転送します。  
  
## <a name="syntax"></a>構文  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Remarks  
 `identifier` で指定されたラベル付きステートメントは、現在の関数内にある必要があります。 すべての `identifier` 名は内部の名前空間のメンバーであるため、他の識別子と干渉することはありません。  
  
 ステートメント ラベルにのみ意味のある、 **goto**ステートメントです。 それ以外の場合、ステートメント ラベルは無視されます。 ラベルは再宣言できません。  
  
 使用するスタイルのプログラミングをお勧め、 **break**、**続行**と**返す**ステートメントの代わりに、 **goto**ステートメントたびに考えられる。 ただし、ため、 **break**ステートメント、ループの 1 つだけのレベルから抜けるを使用する必要があります、 **goto**深く入れ子になったループを終了するステートメント。  
  
 ラベルの詳細については、 **goto**ステートメントを参照してください[ラベル付きステートメント](../cpp/labeled-statements.md)します。  
  
## <a name="example"></a>例  
 この例で、 **goto**ステートメントに制御というラベルの位置を転送`stop`とき`i`が 3 に等しい。  
  
```cpp  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>関連項目  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)