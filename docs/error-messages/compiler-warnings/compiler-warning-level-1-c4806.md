---
title: コンパイラの警告 (レベル 1) C4806 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b580500c3887fe60b7864280ad5ca1804752f2ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062606"
---
# <a name="compiler-warning-level-1-c4806"></a>コンパイラの警告 (レベル 1) C4806

'operation': 安全でない演算: 'type' 型から 'type' 型への上位変換を行うと与えられた定数に等しくなりません

このメッセージは、 `b == 3`に `b` 型がある `bool`などのコードに対して警告を行います。 上位変換の規則に従って、 `bool` が `int`に上位変換されます。 これは有効ですが、 **true**にすることはできません。 次の例では C4806 が生成されます。

```
// C4806.cpp
// compile with: /W1
int main()
{
   bool b = true;
   // try..
   // int b = true;

   if (b == 3)   // C4806
   {
      b = false;
   }
}
```