---
title: コンパイラ エラー C2765 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2765
dev_langs:
- C++
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 708a4c326e87cf580208e26ef5ffe540afd52f95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085135"
---
# <a name="compiler-error-c2765"></a>コンパイラ エラー C2765

'function': 関数テンプレートの明示的な特殊化は、既定の引数を持つことはできません

既定の引数は関数テンプレートの明示的な特殊化では許可されません。 詳細については、次を参照してください。[関数テンプレートの明示的な特殊化](../../cpp/explicit-specialization-of-function-templates.md)します。

次の例では、C2765 が生成されます。

```
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```