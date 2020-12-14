---
description: '詳細情報: コンパイラの警告 (レベル 4) C4429'
title: コンパイラの警告 (レベル 4) C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: dbd552eb2f8e021f8bf7b7747e2a8aee49bb05a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241366"
---
# <a name="compiler-warning-level-4-c4429"></a>コンパイラの警告 (レベル 4) C4429

不完全または不適切な形式のユニバーサル文字名です。

コンパイラは、正しくない形式のユニバーサル文字名である可能性がある文字シーケンスを検出しました。 ユニバーサル文字名の `\u` 後には、4桁の16進数、またはそれに `\U` 続く8桁の16進数が続きます。

次の例では、C4429 が生成されます。

```cpp
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```
