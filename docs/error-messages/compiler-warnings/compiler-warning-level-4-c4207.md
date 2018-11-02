---
title: コンパイラの警告 (レベル 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: 44f49705bf197d7a42b80e50983e47a4c0ce7bed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541125"
---
# <a name="compiler-warning-level-4-c4207"></a>コンパイラの警告 (レベル 4) C4207

使用される標準の拡張機能: 初期化子フォームを拡張

可変長配列を初期化するには、Microsoft 拡張機能 (/Ze)、`char`中かっこ内の文字列を使用します。

## <a name="example"></a>例

```
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

このような初期化が有効で ANSI 互換でない ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。