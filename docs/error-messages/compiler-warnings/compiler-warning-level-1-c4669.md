---
description: '詳細情報: コンパイラの警告 (レベル 1) C4669'
title: コンパイラの警告 (レベル 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: 590c013aed522544462141346ed9b58991d26ed3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164316"
---
# <a name="compiler-warning-level-1-c4669"></a>コンパイラの警告 (レベル 1) C4669

'cast' : 変換が安全ではありません: 'class' はマネージド型または WinRT 型のオブジェクトです

キャストに Windows ランタイム型またはマネージド型が含まれています。 コンパイラは、ポインター間でビット単位のコピーを実行してキャストを完了しますが、他のチェックは行われません。 この警告を解決するには、マネージド メンバーまたは Windows ランタイム型を含むクラスをキャストしないでください。

次の例では、C4669 を生成し、その修正方法を示しています。

```cpp
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```
