---
title: コンパイラの警告 (レベル 4) C4214
ms.date: 11/04/2016
f1_keywords:
- C4214
helpviewer_keywords:
- C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
ms.openlocfilehash: 31711d3709b7c2ae3658d760f538ea9e841d33a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655729"
---
# <a name="compiler-warning-level-4-c4214"></a>コンパイラの警告 (レベル 4) C4214

使用される標準の拡張機能: int 型以外のフィールド型のビット

既定の Microsoft 拡張 (/Ze) で、任意の整数型の構造体メンバーのビット フィールドができます。

## <a name="example"></a>例

```
// C4214.c
// compile with: /W4
struct bitfields
{
   unsigned short j:4;  // C4214
};

int main()
{
}
```

このようなビット フィールドは ANSI 互換の無効な ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。