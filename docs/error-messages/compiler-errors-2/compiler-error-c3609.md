---
title: コンパイラ エラー C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 5572f39082e2dcd8746bb464595c5c00e2f77356
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556444"
---
# <a name="compiler-error-c3609"></a>コンパイラ エラー C3609

'member': sealed 関数または final 関数は仮想である必要があります

[シール](../../windows/sealed-cpp-component-extensions.md)と[最終的な](../../cpp/final-specifier.md)キーワードは、マークされたクラス、構造体、またはメンバー関数でのみ使用できます。`virtual`します。

次の例では C3609 が生成されます。

```
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
