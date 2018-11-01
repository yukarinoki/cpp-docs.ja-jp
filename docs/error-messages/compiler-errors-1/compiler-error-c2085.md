---
title: コンパイラ エラー C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: a65e3c0ea622950b99b9ba83fc168b4718d13e46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560161"
---
# <a name="compiler-error-c2085"></a>コンパイラ エラー C2085

'identifier': 仮パラメーター リストではなく

識別子は、仮パラメーター リストではなく、関数定義で宣言されました。 (ANSI C のみ)

次の例では、C2085 が生成されます。

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

考えられる解決方法:

```
// C2085b.c
void func1( void );
int main( void ) {}
```

セミコロンの欠落している`func1()`ため次の関数の定義、プロトタイプのように`main`内で定義されて`func1()`、識別子のエラー C2085 を生成する`main`。