---
description: 詳細については、「コンパイラエラー C3856」を参照してください。
title: コンパイラ エラー C3856
ms.date: 11/04/2016
f1_keywords:
- C3856
helpviewer_keywords:
- C3856
ms.assetid: 242d9322-c325-4f20-be58-b2be6da56d60
ms.openlocfilehash: f15dbb4029a8eb0c8571e11dda71b3352a834117
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328126"
---
# <a name="compiler-error-c3856"></a>コンパイラ エラー C3856

' type ': クラスはクラス型ではありません

このエラーの最も一般的な原因は、宣言の時点ではなく、定義の時点でジェネリックまたはテンプレートのパラメーターリストが多い場合です。

次の例では、C3856 が生成されます。

```cpp
// C3856.cpp
template <class T>
struct S {
   template <class T1>
   struct S1;
   void f();
};

template <class T>   // C3856
template <class T1>
template <class T2>  // extra template parameter list in definition
struct S<T>::S1{};
```

考えられる解決策:

```cpp
// C3856b.cpp
// compile with: /c
template <class T>
struct S {
   template <class T1>
   struct S1;
   void f();
};

template <class T>
template <class T1>
struct S<T>::S1{};
```

C3856 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
// C3856c.cpp
// compile with: /clr
generic <class T>
ref struct GS {
   generic <class U>
   ref struct GS2;
};

generic <class T>
generic <class U>
generic <class V>
ref struct GS<T>::GS2 {};   // C3856
```

考えられる解決策:

```cpp
// C3856d.cpp
// compile with: /clr /c
generic <class T>
ref struct GS {
   generic <class U>
   ref struct GS2;
};

generic <class T>
generic <class U>
ref struct GS<T>::GS2 {};
```
