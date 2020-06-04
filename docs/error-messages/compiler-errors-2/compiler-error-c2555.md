---
title: コンパイラ エラー C2555
description: Visual Studio C++ コンパイラ エラー C2555 のリファレンス。
ms.date: 03/30/2020
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: fe0e6379e783387506e6098c9b14a047baa8e6c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374183"
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555

> '*クラス 1*::*function1*': オーバーライド仮想関数の戻り値の型が異なり、 ' class2 ::*function2*' と共変ではありません。*function2*

仮想関数と派生オーバーライド関数は、パラメーター リストは同一ですが、戻り値の型は異なります。

## <a name="remarks"></a>解説

C++ では、派生クラスのオーバーライド関数は、基本クラスの仮想関数からの戻り値の型によってのみ異なる場合があります。

この規則には、特定の戻り値の型に対する例外があります。 派生クラスがパブリック基本クラスをオーバーライドする場合、基本クラスのポインターまたは参照ではなく、派生クラスへのポインターまたは参照を返す場合があります。 これらの戻り値の型は、型と共に変化するため、*共変と*呼ばれます。 このルール例外では、共変参照からポインターへの参照、またはポインターへのポインター型は許可されません。

エラーを解決する 1 つの方法は、基本クラスと同じ型を返す方法です。 次に、仮想関数が呼び出された後に戻り値をキャストします。 もう 1 つは、パラメーター リストを変更して、派生クラスのメンバー関数をオーバーライドではなくオーバーロードにすることです。

## <a name="examples"></a>例

を使用して**`/clr`** コンパイルすると、このエラーが表示されることがあります。 たとえば、C++ は次の C# 宣言と等価です。

```csharp
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

```cpp
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

次のサンプルでは、C2555 が生成されます。

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

この問題を修正するには、戻り値`Y::func`の`void`型を に変更します。
