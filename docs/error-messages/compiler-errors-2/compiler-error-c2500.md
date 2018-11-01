---
title: コンパイラ エラー C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: a5753fc99efcdb1064a21981c62faaba84d44189
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468368"
---
# <a name="compiler-error-c2500"></a>コンパイラ エラー C2500

'identifier1': 'identifier2' である直接の基本クラス

クラスまたは構造体は、基本クラスの一覧で複数回表示されます。

直接の基本クラスは基底のリストに記載されています。 間接基底は、基底のリスト内のクラスのいずれかの基本クラスです。

クラスは、直接基底クラスとして複数回指定することはできません。 クラスは、2 回以上の間接基底クラスとして使用できます。

次の例では、C2500 が生成されます。

```
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```