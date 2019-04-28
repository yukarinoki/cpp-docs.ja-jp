---
title: コンパイラの警告 (レベル 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: c737a48883b97970af70014e2bda4bdc508ab471
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207569"
---
# <a name="compiler-warning-level-1-c4228"></a>コンパイラの警告 (レベル 1) C4228

使用される標準の拡張機能: 宣言リスト内のコンマの後に修飾子は無視されます

修飾子の使用などの**const**または`volatile`変数を宣言するときに、コンマが、Microsoft 拡張機能 ([/Ze](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="example"></a>例

```
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```