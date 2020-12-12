---
description: 詳細については、「コンパイラエラー C2990」を参照してください。
title: コンパイラ エラー C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 80aa15940420e9d3e452f2c3a93eefe94fd1561b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328251"
---
# <a name="compiler-error-c2990"></a>コンパイラ エラー C2990

' class ': クラス型として既に宣言されているクラス以外の型

非ジェネリッククラスまたはテンプレートクラスは、ジェネリッククラスまたはテンプレートクラスを再定義します。 ヘッダーファイルの競合を確認します。

次の例では、C2990 が生成されます。

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

C2990 は、Visual Studio 2005 の Microsoft C++ コンパイラの互換性に影響する変更のために発生することもあります。コンパイラでは、同じ型の複数の宣言がテンプレートの仕様に関して同一である必要があります。

次の例では、C2990 が生成されます。

```cpp
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```
