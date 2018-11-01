---
title: コンパイラ エラー C2731
ms.date: 11/04/2016
f1_keywords:
- C2731
helpviewer_keywords:
- C2731
ms.assetid: 9b563999-febd-4582-9147-f355083c091e
ms.openlocfilehash: 2bb00f972f4c12a00255a9820a768d01691f9940
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655034"
---
# <a name="compiler-error-c2731"></a>コンパイラ エラー C2731

'identifier': 関数はオーバー ロードできません

関数は、 `main`、 `WinMain`、 `DllMain`、および`LibMain`オーバー ロードできません。

次の例では、C2731 が生成されます。

```
// C2731.cpp
extern "C" void WinMain(int, char *, char *);
void WinMain(int, short, char *, char*);   // C2731
```