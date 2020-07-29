---
title: コンパイラ エラー C2555
description: Visual Studio C++ コンパイラエラー C2555 のリファレンス。
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ecac92bc663a6344e9ddafe13c194a92ab944c51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207798"
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555

> '*class1*::*function1*': オーバーライドする仮想関数の戻り値の型が異なり、'*class2*::*function2*' からの共変ではありません

仮想関数と派生オーバーライド関数のパラメーターリストが同じですが、戻り値の型が異なります。

## <a name="remarks"></a>解説

C++ では、派生クラスのオーバーライドする関数は、基底クラスの仮想関数の戻り値の型によってのみ異なることはできません。

特定の戻り値の型に対しては、この規則には例外があります。 派生クラスがパブリック基底クラスをオーバーライドすると、基底クラスのポインターまたは参照ではなく、派生クラスへのポインターまたは参照が返されることがあります。 これらの戻り値の型は、型と共に異なるため、*共変*と呼ばれます。 このルール例外では、共変の参照からポインター型またはポインターからポインター型への参照は許可されません。

このエラーを解決する方法の1つは、基本クラスと同じ型を返すことです。 次に、仮想関数が呼び出された後に、戻り値をキャストします。 別の方法として、パラメーターリストを変更して、派生クラスのメンバー関数がオーバーライドではなくオーバーロードになるようにすることもできます。

## <a name="examples"></a>例

を使用してコンパイルすると、このエラーが表示されることがあり **`/clr`** ます。 たとえば、C++ は次の C# 宣言に相当します。

```csharp
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```cpp
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

次の例では、C2555 が生成されます。

```cpp
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```

これを修正するには、の戻り値の型 `Y::func` をに変更し **`void`** ます。
