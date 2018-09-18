---
title: コンパイラの警告 (レベル 1) C4010 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52449689d329cee45cc69b63c315ce9335befbe0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073103"
---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010

単一行コメントには、行連結文字が含まれています。

導入された単一行のコメント//、円記号が含まれています (\\) 行連結文字として機能します。 コンパイラは、続きとなる次の行を考慮し、コメントとして扱われます。

いくつか構文エディターは、コメントとして連結文字の次の行を示していません。 構文の色分けで、この警告が発生した行を無視します。

次の例では、C4010 が生成されます。

```
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```