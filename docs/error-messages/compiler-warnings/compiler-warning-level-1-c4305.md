---
title: コンパイラの警告 (レベル 1) C4305 |Microsoft Docs
ms.custom: ''
ms.date: 1/17/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4305
dev_langs:
- C++
helpviewer_keywords:
- C4305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88ae0fb38b7e6af14525906e90486a68ce22ee56
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086825"
---
# <a name="compiler-warning-level-1-c4305"></a>コンパイラの警告 (レベル 1) C4305

> '*コンテキスト*': から切り捨て'*type1*'to'*type2*'

## <a name="remarks"></a>Remarks

情報の損失より小さい型に初期化またはコンス トラクターの引数としてに値が変換されるとき、この警告が発行されます。

## <a name="example"></a>例

このサンプルには、この警告が表示される 2 つの方法が示します。

```cpp
// C4305.cpp
// Compile by using: cl /EHsc /W4 C4305.cpp

struct item
{
    item(float) {}
};

int main()
{
    float f = 2.71828;          // C4305 'initializing'
    item i(3.14159);            // C4305 'argument'
    return static_cast<int>(f);
}
```

この問題を解決するには、適切な型の値を使用して初期化するか、適切な型に明示的なキャストを使用します。 などを使用して、 **float**リテラルの代わりに 2.71828f など、**二重**(浮動小数点リテラルの既定の種類) 初期化するために、 **float**変数、またはに渡す、受け取るコンス トラクター、 **float**引数。
