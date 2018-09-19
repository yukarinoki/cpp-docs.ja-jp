---
title: while ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while_cpp
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76820d46940927aab20856fef6fdbbf28539451f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097758"
---
# <a name="while-statement-c"></a>while ステートメント (C++)

実行*ステートメント*まで繰り返し*式*0 に評価します。

## <a name="syntax"></a>構文

```
while ( expression )
   statement
```

## <a name="remarks"></a>Remarks

テスト*式*ループの各実行前に、の処理を行うのため、**中に**ループは 0 回以上を実行します。 *式*の整数型、ポインター型、または整数への明確な変換を持つクラス型またはポインター型である必要があります。

A**中に**ループがときに終了することできますも、 [break](../cpp/break-statement-cpp.md)、 [goto](../cpp/goto-statement-cpp.md)、または[を返す](../cpp/return-statement-cpp.md)ステートメント本体が実行されます。 使用[続行](../cpp/continue-statement-cpp.md)を終了する前に、現在のイテレーションを終了する、**中**ループします。 **引き続き**の次のイテレーションに制御を渡します、**中**ループします。

次のコードでは、**中**文字列から末尾をトリミングするループがアンダー スコアします。

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

終了条件はループの先頭で評価されます。 末尾のアンダースコアがない場合、ループは実行されません。

## <a name="see-also"></a>関連項目

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for ステートメント (C++)](../cpp/for-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)