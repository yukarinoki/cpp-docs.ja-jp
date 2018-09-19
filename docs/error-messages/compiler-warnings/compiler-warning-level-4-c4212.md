---
title: コンパイラの警告 (レベル 4) C4212 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4212
dev_langs:
- C++
helpviewer_keywords:
- C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 107581742f1a60cfc015a9a1b8ccea8b2f89c7a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074761"
---
# <a name="compiler-warning-level-4-c4212"></a>コンパイラの警告 (レベル 4) C4212

標準の拡張機能を使用: 関数宣言は、省略記号を使用

関数プロトタイプには可変個の引数。 関数定義されていません。

次の例では、C4212 が生成されます。

```
// C4212.c
// compile with: /W4 /Ze /c
void f(int , ...);
void f(int i, int j) {}
```