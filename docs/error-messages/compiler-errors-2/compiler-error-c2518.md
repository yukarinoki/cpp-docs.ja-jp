---
title: コンパイラ エラー C2518
ms.date: 11/04/2016
f1_keywords:
- C2518
helpviewer_keywords:
- C2518
ms.assetid: a7895b47-da90-4851-ac97-18e81479595a
ms.openlocfilehash: 315edc3124b4cdd425ce9d7581167366d3831512
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214647"
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
