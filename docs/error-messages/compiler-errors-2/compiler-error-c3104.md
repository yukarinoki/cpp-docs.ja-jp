---
description: 詳細については、「コンパイラエラー C3104」を参照してください。
title: コンパイラ エラー C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: b093c5daa96a4c0e9bf789dfcc67ac6b6d3f2561
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116094"
---
# <a name="compiler-error-c3104"></a>コンパイラ エラー C3104

無効な属性引数です

属性に無効な引数が指定されました。

詳細については、「 [属性パラメーターの型](../../extensions/attribute-parameter-types-cpp-component-extensions.md) 」を参照してください。

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される場合があります。マネージ配列をカスタム属性に渡すときに、配列の型が集計初期化リストから推測されなくなりました。 コンパイラでは、初期化子リストだけでなく、配列の型も指定する必要があります。

## <a name="examples"></a>例

次の例では、C3104 が生成されます。

```cpp
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

次の例では、C3104 が生成されます。

```cpp
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```
