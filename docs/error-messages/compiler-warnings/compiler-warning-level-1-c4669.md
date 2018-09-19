---
title: コンパイラの警告 (レベル 1) C4669 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4669
dev_langs:
- C++
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f96bcf40b1fbc989daceabc810d019d1bb9aa98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060859"
---
# <a name="compiler-warning-level-1-c4669"></a>コンパイラの警告 (レベル 1) C4669

'cast' : 変換が安全ではありません: 'class' はマネージド型または WinRT 型のオブジェクトです

キャストに Windows ランタイム型またはマネージド型が含まれています。 コンパイラは、ポインター間でビット単位のコピーを実行してキャストを完了しますが、他のチェックは行われません。 この警告を解決するには、マネージド メンバーまたは Windows ランタイム型を含むクラスをキャストしないでください。

次の例では、C4669 を生成し、その修正方法を示しています。

```
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