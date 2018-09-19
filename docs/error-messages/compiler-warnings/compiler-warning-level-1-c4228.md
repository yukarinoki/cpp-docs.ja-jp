---
title: コンパイラの警告 (レベル 1) C4228 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4228
dev_langs:
- C++
helpviewer_keywords:
- C4228
ms.assetid: 9301d660-d601-464e-83f5-7ed844a3c6dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab568ef6622bfa10f0e10566ec92dfaee71d22c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047955"
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