---
description: 詳細については、「コンパイラエラー C3174」を参照してください。
title: コンパイラ エラー C3174
ms.date: 11/04/2016
f1_keywords:
- C3174
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
ms.openlocfilehash: 28a2daae597e93d8aa3745ad16eed491e3ea2e87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242094"
---
# <a name="compiler-error-c3174"></a>コンパイラ エラー C3174

モジュール属性が指定されませんでした

Visual C++ の属性を使用するプログラムでは、属性を使用するすべてのプログラムで必要とされる [module](../../windows/attributes/module-cpp.md) 属性も使用しませんでした。

次の例では、C3174 が生成されます。

```cpp
// C3174.cpp
// C3174 expected
// uncomment the following line to resolve this C3174
// [module(name="x")];
[export]
struct S
{
   int i;
};

int main()
{
}
```
