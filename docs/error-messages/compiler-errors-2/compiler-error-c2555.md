---
title: コンパイラ エラー C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ebf3e4a3aff48311edd5fb95b01a7b2d23990231
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202425"
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555

' class1:: function1 ': オーバーライドする仮想関数の戻り値の型が異なり、' class2:: function2 ' からの共変ではありません

仮想関数と派生オーバーライド関数のパラメーターリストが同じですが、戻り値の型が異なります。 派生クラスのオーバーライドする関数は、戻り値の型によってのみ、基底クラスの仮想関数と異なることはできません。

このエラーを解決するには、仮想関数が呼び出された後に戻り値をキャストします。

また、/clr を使用してコンパイルすると、このエラーが表示されることがあります。   たとえば、次の宣言C++に相当するビジュアルC#は次のようになります。

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

:

```
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
