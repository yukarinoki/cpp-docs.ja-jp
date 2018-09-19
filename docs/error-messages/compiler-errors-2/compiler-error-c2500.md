---
title: コンパイラ エラー C2500 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b7e24ca520796b63171fe63c2bf841fe8776845
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026674"
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