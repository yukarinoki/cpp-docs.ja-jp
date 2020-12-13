---
description: '詳細情報: コンパイラの警告 (レベル 1) C4006'
title: コンパイラの警告 (レベル 1) C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: 1d0b38e2ac3d224f26a0a52ac2d7f2343a1f955d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335981"
---
# <a name="compiler-warning-level-1-c4006"></a>コンパイラの警告 (レベル 1) C4006

\#undef には識別子が必要です

`#undef` ディレクティブは未定義にする識別子を指定しませんでした。 ディレクティブは無視されます。 この警告を解決するには、必ず識別子を指定します。 次の例では C4006 が生成されます。

```cpp
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```
