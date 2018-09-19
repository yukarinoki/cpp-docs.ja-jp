---
title: コンパイラ エラー C2062 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbda0894b25e09681207d6447bb40727d490fc02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072252"
---
# <a name="compiler-error-c2062"></a>コンパイラ エラー C2062

型 'type' の予期しません。

コンパイラは、型名を予期していません。

次の例では、C2062 が生成されます。

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 発生することもまた、コンパイラの方法は、コンス トラクターのパラメーター リストで定義されていない型の処理。 コンパイラには、未定義の型 (スペル ミスですか?) が発生すると、コンス トラクターは、式を指定し、c2062 と仮定します。 を解決するには、コンス トラクターのパラメーター リストで定義された型をのみ使用します。