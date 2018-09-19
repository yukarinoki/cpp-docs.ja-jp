---
title: コンパイラ エラー C2562 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2562
dev_langs:
- C++
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69151b71de84c678c09ecafe099344a08d28a8a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114229"
---
# <a name="compiler-error-c2562"></a>コンパイラ エラー C2562

'identifier': 'void' 関数の値を返す

関数として`void`が値を返します。

このエラーは、間違った関数プロトタイプで発生することができます。

このエラーは、関数の宣言で戻り値の型を指定する場合に解決される可能性があります。

次の例では、C2562 が生成されます。

```
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```