---
description: 詳細については、「コンパイラエラー C3353」を参照してください。
title: コンパイラ エラー C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 50ff7a6b104f3e16ce17f1398da49a146c0d41a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335042"
---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353

'delegate': デリゲートはマネージド型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます

[Delegate](../../extensions/delegate-cpp-component-extensions.md)キーワードで宣言されたデリゲートは、グローバルスコープでのみ宣言できます。

次の例では C3353 が生成されます。

```cpp
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```
