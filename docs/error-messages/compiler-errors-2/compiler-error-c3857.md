---
description: 詳細については、「コンパイラエラー C3857」を参照してください。
title: コンパイラ エラー C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 6d4dacfc8bf18f7f2b9665058bbd418eb0615912
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336130"
---
# <a name="compiler-error-c3857"></a>コンパイラ エラー C3857

' type ': 複数の型パラメーターリストは使用できません

同じ型に対して複数のテンプレートまたはジェネリックが指定されていますが、これは許可されていません。

次の例では、C3857 が生成されます。

```cpp
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

考えられる解決策:

```cpp
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

考えられる解決策:

```cpp
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```
