---
title: コンパイラの警告 (レベル 4) C4202 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4202
dev_langs:
- C++
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd44b436369e908d471ff56d193f3afab97a769
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103311"
---
# <a name="compiler-warning-level-4-c4202"></a>コンパイラの警告 (レベル 4) C4202

標準の拡張機能を使用します。 '…': プロトタイプのパラメーター名の一覧が不正です。

旧式の関数定義には、可変個の引数が含まれています。 これらの定義は、ANSI 互換のエラーを生成 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="example"></a>例

```
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```