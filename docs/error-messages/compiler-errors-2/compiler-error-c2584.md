---
description: 詳細については、「コンパイラエラー C2584」を参照してください。
title: コンパイラ エラー C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 7820019c3ec49928f59980adbd9ec814d67c3499
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177680"
---
# <a name="compiler-error-c2584"></a>コンパイラ エラー C2584

' Class ': direct base ' Base2 ' にアクセスできません。' Base1 ' のベースが既にあります

`Class` はから直接派生 `Base1` しています。 `Base2` もから派生 `Base1` します。 `Class``Base2` `Base1` は、既に直接の基底クラスであるため、から派生できません。これは、から間接的に (間接的に) 継承されることを意味 `Base1` します。

## <a name="example"></a>例

次の例では、C2584 が生成されます。

```cpp
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```
