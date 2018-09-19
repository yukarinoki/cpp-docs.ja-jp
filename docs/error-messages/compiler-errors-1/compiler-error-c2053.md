---
title: コンパイラ エラー C2053 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 711debdfe82db617e7974afbfb75b2116eec0260
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101998"
---
# <a name="compiler-error-c2053"></a>コンパイラ エラー C2053

'identifier': ワイド文字列が一致しません

ワイド文字列は、互換性のない型に割り当てられます。

次の例では、C2053 が生成されます。

```
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```