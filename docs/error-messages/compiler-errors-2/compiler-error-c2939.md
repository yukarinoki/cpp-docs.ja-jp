---
title: コンパイラ エラー C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 59b2f63ba12a644f13b3586fbf6eec4d5bfa8be5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302658"
---
# <a name="compiler-error-c2939"></a>コンパイラ エラー C2939

'class': type-class-id が、ローカル データ変数として再定義されています

ジェネリック クラスまたはテンプレート クラスをローカル データ変数として使用することはできません。

このエラーは、中かっこが正しく一致していない場合に発生することがあります。

次の例では C2939 が生成されます。

```
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

C2939 は、ジェネリックを使用する場合にも発生することがあります。

```
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```