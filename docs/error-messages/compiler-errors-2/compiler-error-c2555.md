---
title: コンパイラ エラー C2555 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0cd401aa1ee3611befb39d630f48f6aed36211c
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889947"
---
# <a name="compiler-error-c2555"></a>コンパイラ エラー C2555

'class1::function1': 仮想関数をオーバーライドする型の戻り値とは異なる 'class2::function2' の covariant ではありません

仮想関数、派生のオーバーライド関数戻り値の型が同一のパラメーター リストであります。 派生クラスでオーバーライドする関数は、戻り値の型によってのみ、基本クラスの仮想関数と異なることはできません。

このエラーを解決するには、仮想関数が呼び出された後、戻り値をキャストします。

/Clr でコンパイルする場合は、このエラーも表示可能性があります。   たとえば、Visual c 次の c# 宣言と同等です。

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

is

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