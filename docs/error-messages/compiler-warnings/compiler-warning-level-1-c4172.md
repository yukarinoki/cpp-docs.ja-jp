---
title: コンパイラの警告 (レベル 1) C4172 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4172
dev_langs:
- C++
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56f606b48fb060472dd67d34800c06946bc41712
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043509"
---
# <a name="compiler-warning-level-1-c4172"></a>コンパイラの警告 (レベル 1) C4172

ローカル変数またはテンポラリのアドレスを返します。

関数は、ローカル変数または一時オブジェクトのアドレスを返します。 返されたアドレスが有効でないために、ローカル変数と一時オブジェクトが関数から制御が戻るときに破棄されます。

関数は、ローカル オブジェクトのアドレスを返さないように再設計します。

次の例では、C4172 が生成されます。

```
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```