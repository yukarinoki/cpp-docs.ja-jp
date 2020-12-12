---
description: 詳細については、「コンパイラエラー C2939」を参照してください。
title: コンパイラ エラー C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 465d2d9535a1c8f393e21b4ef48707f8e5fab89b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323026"
---
# <a name="compiler-error-c2939"></a>コンパイラ エラー C2939

'class': type-class-id が、ローカル データ変数として再定義されています

ジェネリック クラスまたはテンプレート クラスをローカル データ変数として使用することはできません。

このエラーは、中かっこが正しく一致していない場合に発生することがあります。

次の例では C2939 が生成されます。

```cpp
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

C2939 は、ジェネリックを使用する場合にも発生することがあります。

```cpp
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```
