---
title: コンパイラ エラー C3224 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3224
dev_langs:
- C++
helpviewer_keywords:
- C3224
ms.assetid: 129be22f-8f3e-4fc6-9ccd-d27d8ef91251
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7eb7c5d9bc912eafb2c7772114448a0567d90cad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105038"
---
# <a name="compiler-error-c3224"></a>コンパイラ エラー C3224

'type': オーバーロードされたジェネリック クラスには、'number' ジェネリック型引数を指定できません

コンパイラは、適切なオーバーロードを見つけることができませんでした。

次の例では C3224 が生成されます。

```
// C3224.cs
// compile with: /target:library
public class C<T> {}
public class C<T,U> {}
```

この場合、次のようになります。

```
// C3224b.cpp
// compile with: /clr
#using "C3224.dll"
int main() {
   C<int,int,int>^ c = gcnew C<int,int,int>();   // C3224
   C<int,int>^ c2 = gcnew C<int,int>();   // OK
}
```