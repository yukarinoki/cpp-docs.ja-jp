---
description: 詳細については、「コンパイラエラー C2936」を参照してください。
title: コンパイラ エラー C2936
ms.date: 11/04/2016
f1_keywords:
- C2936
helpviewer_keywords:
- C2936
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
ms.openlocfilehash: 2c01886ac02cdd772e7c92faa15dbd015aa6e6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323039"
---
# <a name="compiler-error-c2936"></a>コンパイラ エラー C2936

'class': type-class-id がグローバル データ変数として再定義されています

ジェネリック クラスまたはテンプレート クラスをグローバル データ変数として使用することはできません。

このエラーは、中かっこが正しく一致していない場合に発生することがあります。

次の例では C2936 が生成されます。

```cpp
// C2936.cpp
// compile with: /c
template<class T> struct TC { };
int TC<int>;   // C2936

// OK
struct TC2 { };
int TC2;
```

C2936 は、ジェネリックを使用している場合にも発生することがあります。

```cpp
// C2936b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
int GC<int>;   // C2936

// OK
ref struct GC2 {};
int GC2;
```
