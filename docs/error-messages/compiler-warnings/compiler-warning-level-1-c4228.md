---
title: コンパイラの警告 (レベル 1) C4228
ms.date: 11/04/2016
f1_keywords:
- C4228
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
ms.openlocfilehash: 3a89d5c0924e6fd12a4ccf8afa957f8908670d49
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223240"
---
# <a name="compiler-warning-level-1-c4228"></a>コンパイラの警告 (レベル 1) C4228

非標準の拡張機能が使用されています: 宣言子リストのコンマの後の修飾子は無視されます

変数を宣言するときのコンマのような修飾子の使用は **`const`** **`volatile`** 、Microsoft 拡張機能 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) です。

## <a name="example"></a>例

```cpp
// C4228.cpp
// compile with: /W1
int j, const i = 0;  // C4228
int k;
int const m = 0;  // ok
int main()
{
}
```
