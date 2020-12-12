---
description: 詳細については、「コンパイラエラー C2937」を参照してください。
title: コンパイラ エラー C2937
ms.date: 11/04/2016
f1_keywords:
- C2937
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
ms.openlocfilehash: af73e4564293fdcd5b69cc2f1890cb3e5364c618
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323052"
---
# <a name="compiler-error-c2937"></a>コンパイラ エラー C2937

'class': type-class-id がグローバル typedef として再定義されています

ジェネリッククラスまたはテンプレートクラスをグローバルとして使用することはできません **`typedef`** 。

次の例では C2937 が生成されます。

```cpp
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

C2937 は、ジェネリックを使用しているときも発生する場合があります。

```cpp
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```
