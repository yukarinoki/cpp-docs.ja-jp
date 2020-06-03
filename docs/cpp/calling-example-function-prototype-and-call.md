---
title: '呼び出しの例: 関数プロトタイプと呼び出し'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: c41d7679be8b7faa3c8df1368d14815a1b840284
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190171"
---
# <a name="calling-example-function-prototype-and-call"></a>呼び出しの例: 関数プロトタイプと呼び出し

**Microsoft 固有の仕様**

次の例では、さまざまな呼び出し規約を使用して関数呼び出しを行った結果を示しています。

この例は、次の関数スケルトンに基づいています。 `calltype` は適切な呼び出し規約に置き換えます。

```cpp
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

詳細については、「[呼び出し例の結果](../cpp/results-of-calling-example.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[呼び出し規約](../cpp/calling-conventions.md)
