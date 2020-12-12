---
description: 詳細については、「コンパイラエラー C3609」を参照してください。
title: コンパイラ エラー C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 187bc6d9849c385f6adb3ae2c25e2e90e7393e6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223127"
---
# <a name="compiler-error-c3609"></a>コンパイラ エラー C3609

'member': sealed 関数または final 関数は仮想である必要があります

[Sealed](../../extensions/sealed-cpp-component-extensions.md)および [final](../../cpp/final-specifier.md)キーワードは、とマークされたクラス、構造体、またはメンバー関数でのみ使用でき **`virtual`** ます。

次の例では C3609 が生成されます。

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
