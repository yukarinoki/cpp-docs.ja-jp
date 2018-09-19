---
title: コンパイラ エラー C2502 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2502
dev_langs:
- C++
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f5e3197ca71ff277f2904666261e7d0546a9128f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032532"
---
# <a name="compiler-error-c2502"></a>コンパイラ エラー C2502

'identifier': 基底クラスでアクセス修飾子が多すぎます

基本クラスには、1 つ以上のアクセス修飾子があります。 1 つのみのアクセス修飾子 (`public`、 `private`、または`protected`) は許可されています。

次の例では、C2502 が生成されます。

```
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```