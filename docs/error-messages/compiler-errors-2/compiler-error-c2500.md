---
description: 詳細については、「コンパイラエラー C2500」を参照してください。
title: コンパイラ エラー C2500
ms.date: 11/04/2016
f1_keywords:
- C2500
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
ms.openlocfilehash: 39d1ab0876470b443d4444a3c583cc0993c98325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275972"
---
# <a name="compiler-error-c2500"></a>コンパイラ エラー C2500

' identifier1 ': ' identifier2 ' は既に直接基底クラスです

クラスまたは構造体が基底クラスのリストに複数回出現します。

直接ベースは、基本リストに記載されています。 間接基本は、基本リスト内のいずれかのクラスの基本クラスです。

クラスは、直接基底クラスとして複数回指定することはできません。 クラスは、間接的な基底クラスとして複数回使用できます。

次の例では、C2500 が生成されます。

```cpp
// C2500.cpp
// compile with: /c
class A {};
class B : public A, public A {};    // C2500

// OK
class C : public A {};
class D : public A {};
class E : public C, public D {};
```
