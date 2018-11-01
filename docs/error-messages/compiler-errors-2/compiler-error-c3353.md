---
title: コンパイラ エラー C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: eb7b55f63e911f155c13e777e2e84ae7b587e9a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432670"
---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353

'delegate': デリゲートはマネージド型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます

使用して、デリゲート宣言、[委任](../../windows/delegate-cpp-component-extensions.md)キーワードは、グローバル スコープでのみ宣言できます。

次の例では C3353 が生成されます。

```
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```