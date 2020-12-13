---
description: 詳細については、「コンパイラエラー C2499」を参照してください。
title: コンパイラ エラー C2499
ms.date: 11/04/2016
f1_keywords:
- C2499
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
ms.openlocfilehash: 35d6c0017792c14b99418166af7ae6a84745340d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335077"
---
# <a name="compiler-error-c2499"></a>コンパイラ エラー C2499

' class ': クラスは、それ自体の基底クラスにすることはできません

定義しようとしているクラスを基底クラスとして指定しようとしました。

次の例では、C2499 が生成されます。

```cpp
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```
