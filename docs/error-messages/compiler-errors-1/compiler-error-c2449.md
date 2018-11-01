---
title: コンパイラ エラー C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: f674bbec7cee8c00792848ee7e51b1e46299dd58
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655331"
---
# <a name="compiler-error-c2449"></a>コンパイラ エラー C2449

検出された '{0}' ファイルのスコープ (関数のヘッダーがありません)。

かっこは、ファイル スコープで発生します。

このエラーは、関数のヘッダーと、関数定義の中かっこの間のセミコロンで発生することができます。

次の例では、C2499 が生成されます。

```
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```