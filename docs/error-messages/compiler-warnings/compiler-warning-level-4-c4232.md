---
title: コンパイラの警告 (レベル 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: dee087b73bf032a68daf0527ea584efcc7579361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552634"
---
# <a name="compiler-warning-level-4-c4232"></a>コンパイラの警告 (レベル 4) C4232

使用される標準の拡張機能: 'identifier': dllimport 'dllimport' のアドレスは静的でありません、保証されません

宣言された関数のアドレスとして Microsoft 拡張機能 (/Ze)、静的でない値を指定したことができます、 **dllimport**修飾子。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、このエラーが発生します。

次の例では、C4232 が生成されます。

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```