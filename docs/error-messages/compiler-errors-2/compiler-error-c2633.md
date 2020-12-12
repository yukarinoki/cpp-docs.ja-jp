---
description: 詳細については、「コンパイラエラー C2633」を参照してください。
title: コンパイラエラー C2633
ms.date: 11/04/2016
f1_keywords:
- C2633
helpviewer_keywords:
- C2633
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
ms.openlocfilehash: 182cafdd9a79744414a89792e1361c8173077705
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123449"
---
# <a name="compiler-error-c2633"></a>コンパイラエラー C2633

' identifier ': ' inline ' は、コンストラクターの唯一の有効なストレージクラスです

コンストラクターがインライン以外のストレージクラスとして宣言されています。

次の例では、C2633 が生成されます。

```cpp
// C2633.cpp
// compile with: /c
class C {
   extern C();   // C2633, not inline
   inline C();   // OK
};
```
