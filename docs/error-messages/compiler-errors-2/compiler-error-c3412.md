---
title: コンパイラ エラー C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: 7c16ffa37f4d7192956afae26c825b63add1bfdd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540249"
---
# <a name="compiler-error-c3412"></a>コンパイラ エラー C3412

'template': 現在のスコープでテンプレートを特殊化できません。

テンプレートは、グローバルでのみ、クラス スコープまたは名前空間スコープで特殊化することはできません。

## <a name="example"></a>例

次の例では、C3412 が生成されます。

```
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

## <a name="example"></a>例

次の例では、考えられる解決策を示します。

```
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```