---
description: 詳細については、「コンパイラエラー C3412」を参照してください。
title: コンパイラ エラー C3412
ms.date: 11/04/2016
f1_keywords:
- C3412
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
ms.openlocfilehash: aa0dc6cfeac193afc99d003cd821663bcfc139c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313191"
---
# <a name="compiler-error-c3412"></a>コンパイラ エラー C3412

' template ': 現在のスコープでテンプレートを特殊化できません

テンプレートはクラススコープで特殊化できません。グローバルまたは名前空間スコープでのみ使用できます。

## <a name="examples"></a>例

次の例では、C3412 が生成されます。

```cpp
// C3412.cpp
template <class T>
struct S {
   template <>
   struct S<int> {};   // C3412 in a class
};
```

次の例は、考えられる解決方法を示しています。

```cpp
// C3412b.cpp
// compile with: /c
template <class T>
struct S {};

template <>
struct S<int> {};
```
