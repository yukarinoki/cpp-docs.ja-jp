---
title: コンパイラ エラー C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 00e103720dc666b17566b67da19d4e908bb3addd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767536"
---
# <a name="compiler-error-c3896"></a>コンパイラ エラー C3896

'member': 正しくない初期化子: このリテラル データ メンバーは 'nullptr' と共にのみ初期化できます

A[リテラル](../../extensions/literal-cpp-component-extensions.md)データ メンバーが正しく初期化されていません。  参照してください[nullptr](../../extensions/nullptr-cpp-component-extensions.md)詳細についてはします。

次の例では、C3896 が生成されます。

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```