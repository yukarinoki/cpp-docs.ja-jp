---
title: コンパイラ エラー C2379 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2379
dev_langs:
- C++
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec340a5a48705eb91bf5bf72ec20ad382f4b262c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032446"
---
# <a name="compiler-error-c2379"></a>コンパイラ エラー C2379

仮パラメーターの数が昇格するときに別の種類

指定したパラメーターの型は、互換性のある、以前の宣言で型の既定のプロモーションが。 これは ANSI C でエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) と Microsoft の拡張機能の警告 (**/Ze**)。

次の例では、C2379 が生成されます。

```
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```