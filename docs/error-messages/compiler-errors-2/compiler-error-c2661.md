---
description: 詳細については、「コンパイラエラー C2661」を参照してください。
title: コンパイラエラー C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: 524d270fd15b529bad13a5ff1e5e46f3d5d9dd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170023"
---
# <a name="compiler-error-c2661"></a>コンパイラエラー C2661

' function ': 数値パラメーターを受け取るオーバーロードされた関数はありません。

次の原因が考えられます。

1. 関数呼び出しの実際のパラメーターが正しくありません。

1. 関数の宣言がありません。

次の例では、C2661 が生成されます。

```cpp
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```
