---
title: コンパイラの警告 (レベル 1) C4224 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4224
dev_langs:
- C++
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49ad5937d310166dd3ca7f41e6881d98f396535f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025661"
---
# <a name="compiler-warning-level-1-c4224"></a>コンパイラの警告 (レベル 1) C4224

使用される標準の拡張機能: 仮パラメーター 'identifier' は型として定義された以前

識別子として使用されていた、`typedef`します。 これにより、ANSI 互換の警告 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="example"></a>例

```
// C4224.cpp
// compile with: /Za /W1 /LD
typedef int I;
void func ( int I );  // C4224
```