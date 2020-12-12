---
description: 詳細については、「コンパイラエラー C2935」を参照してください。
title: コンパイラ エラー C2935
ms.date: 11/04/2016
f1_keywords:
- C2935
helpviewer_keywords:
- C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
ms.openlocfilehash: 853c1e51444454ffdbd09e8387d47eb9770d7fa7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320306"
---
# <a name="compiler-error-c2935"></a>コンパイラ エラー C2935

'class': type-class-id がグローバル関数として再定義されています

ジェネリック クラスまたはテンプレート クラスをグローバル関数として使用することはできません。

このエラーは、中かっこが正しく一致していない場合に発生することがあります。

次の例では C2935 が生成されます。

```cpp
// C2935.cpp
// compile with: /c
template<class T>
struct TC {};
void TC<int>() {}   // C2935

// OK
struct TC2 {};
void TC2() {}
```

C2935 は、ジェネリックを使用しているときも発生します。

```cpp
// C2935b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC { };
void GC<int>() {}   // C2935
void GC() {}   // OK
```
