---
description: '詳細情報: コンパイラの警告 (レベル 4) C4032'
title: コンパイラの警告 (レベル 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 1c150bff398bbd2d6e5f1a8d21211f4c6b4cb6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262101"
---
# <a name="compiler-warning-level-4-c4032"></a>コンパイラの警告 (レベル 4) C4032

昇格時に仮引数 ' number ' の型が異なります

パラメーターの型は、既定の昇格を通じて、前の宣言の型と互換性がありません。

これは、ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) ではエラーであり、Microsoft 拡張機能 (/ze) では警告が発生します。

## <a name="example"></a>例

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
