---
title: コンパイラ エラー C2085 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d88968e49e38a13782dde2d905a614ad4d177e81
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082379"
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