---
description: 詳細については、「コンパイラエラー C2942」を参照してください。
title: コンパイラ エラー C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: d68db30f1b70aed20e2501c88bddaf00bb330149
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249595"
---
# <a name="compiler-error-c2942"></a>コンパイラ エラー C2942

'class': 関数の仮引数として再定義された type-class-id

ジェネリック クラスまたはテンプレート クラスを仮引数として使用することはできません。 ジェネリック クラスまたはテンプレート クラスのコンストラクターに引数を直接渡すことはできません。

次の例では C2942 が生成されます。

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

C2942 は、ジェネリックを使用しているときも発生します。

```cpp
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```
