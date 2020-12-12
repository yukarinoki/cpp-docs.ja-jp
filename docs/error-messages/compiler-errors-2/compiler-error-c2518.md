---
description: 詳細については、「コンパイラエラー C2518」を参照してください。
title: コンパイラ エラー C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: 1ebc270cd3544dc50d051677faeeec8e8e6bd979
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212728"
---
# <a name="compiler-error-c2518"></a>コンパイラ エラー C2518

キーワード ' keyword ' は基底クラスリストでは無効です。無効

キーワードとは、 **`class`** **`struct`** 基底クラスのリストには記述できません。

次の例では、C2518 が生成されます。

```cpp
// C2518.cpp
// compile with: /c
class B {};
class C : public class B {};   // C2518
class D: public B {};   // OK
```
