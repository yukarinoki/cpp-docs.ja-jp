---
title: コンパイラの警告 (レベル 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: 8a3697b3bf63ac2a7a1e4e4bd0bf3a626c6bd631
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401151"
---
# <a name="compiler-warning-level-4-c4213"></a>コンパイラの警告 (レベル 4) C4213

使用される標準の拡張機能: 左辺値のキャスト

既定の Microsoft 拡張 (/Ze) ではキャストを使用して、代入ステートメントの左側にあることができます。

## <a name="example"></a>例

```
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

このようなキャストが有効で ANSI 互換でない ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。