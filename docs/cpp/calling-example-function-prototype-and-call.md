---
title: '呼び出しの例: 関数プロトタイプと呼び出し |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04e681560854be4c93b1c93786d38771c07244ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099578"
---
# <a name="calling-example-function-prototype-and-call"></a>呼び出しの例: 関数プロトタイプと呼び出し

## <a name="microsoft-specific"></a>Microsoft 固有の仕様

次の例では、さまざまな呼び出し規則を使用して関数呼び出しを行った結果を示しています。

この例は、次の関数スケルトンに基づいています。 `calltype` は適切な呼び出し規約に置き換えます。

```
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

詳細については、次を参照してください。[呼び出し結果の例](../cpp/results-of-calling-example.md)します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[呼び出し規約](../cpp/calling-conventions.md)