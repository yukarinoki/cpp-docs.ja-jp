---
title: continue ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88281d90ce15ced12079b3c66a74bb2f23c11034
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099718"
---
# <a name="continue-statement-c"></a>continue ステートメント (C++)

外側にある最小の制御式を強制的にコントロールの転送[は](../cpp/do-while-statement-cpp.md)、[の](../cpp/for-statement-cpp.md)、または[中](../cpp/while-statement-cpp.md)ループします。

## <a name="syntax"></a>構文

```
continue;
```

## <a name="remarks"></a>Remarks

現在のイテレーションの残りのステートメントは実行されません。 ループの次のイテレーションは、次のように決定されます。

- **は**または**中**、ループの制御式を再評価によって次の反復処理が開始されます、**は**または**中に**ステートメント。

- **の**ループ (構文を使用して`for`(`init-expr`;`cond-expr`;`loop-expr`))、`loop-expr`句が実行されます。 次に、`cond-expr` 句が再評価され、その結果に応じて、ループが終了するか、別のイテレーションが発生します。

次の例は、**続行**コードのセクションをバイパスし、ループの次のイテレーションを開始するステートメントを使用できます。

## <a name="example"></a>例

```cpp
// continue_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        i++;
        printf_s("before the continue\n");
        continue;
        printf("after the continue, should never print\n");
     } while (i < 3);

     printf_s("after the do loop\n");
}
```

```Output
before the continue
before the continue
before the continue
after the do loop
```

## <a name="see-also"></a>関連項目

[ジャンプ ステートメント](../cpp/jump-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)