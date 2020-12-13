---
description: 詳細については、「コンパイラエラー C2449」を参照してください。
title: コンパイラ エラー C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: cea4218d71b01a5f93b4c9409175449f78e3211f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332447"
---
# <a name="compiler-error-c2449"></a>コンパイラ エラー C2449

ファイルスコープで ' {' が見つかりました (関数ヘッダーがありませんか?)

ファイルスコープで左中かっこが発生します。

このエラーは、関数ヘッダーと関数定義の左中かっこの間にセミコロンがあると発生することがあります。

次の例では、C2499 が生成されます。

```c
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```
