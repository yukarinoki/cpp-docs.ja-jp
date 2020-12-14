---
description: 詳細については、「コンパイラエラー C2940」を参照してください。
title: コンパイラ エラー C2940
ms.date: 11/04/2016
f1_keywords:
- C2940
helpviewer_keywords:
- C2940
ms.assetid: af6bf2bf-8de6-4cfd-bbf0-4c6b32a30edf
ms.openlocfilehash: 2601e32d2e52d332e4f6443dde23b544d955aac1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249686"
---
# <a name="compiler-error-c2940"></a>コンパイラ エラー C2940

'class': type-class-id がローカル typedef として再定義されています

ジェネリッククラスまたはテンプレートクラスをローカルとして使用することはできません **`typedef`** 。

次の例では C2940 が生成されます。

```cpp
// C2940.cpp
template<class T>
struct TC {};
int main() {
   typedef int TC<int>;   // C2940
   typedef int TC;   // OK
}
```

C2940 は、ジェネリックを使用する場合にも発生することがあります。

```cpp
// C2940b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   typedef int GC<int>;   // C2940
   typedef int GC;
}
```
