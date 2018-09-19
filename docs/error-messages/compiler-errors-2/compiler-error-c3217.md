---
title: コンパイラ エラー C3217 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3217
dev_langs:
- C++
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c407e8f77990bdbeea143c252a27292ac282497e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063490"
---
# <a name="compiler-error-c3217"></a>コンパイラ エラー C3217

'param' : ジェネリック パラメーターは、この宣言内で制限されることはできません

制約の形式が正しくありません。制約のジェネリック パラメーターは、ジェネリック クラスのテンプレート パラメーターと一致している必要があります。

次の例では C3217 が生成されます。

```
// C3217.cpp
// compile with: /clr
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T : A   // C3217
   void f();
};
```

次の例では、考えられる解決策を示しています。

```
// C3217b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
ref class C {
   generic <class T1>
   where T1 : A
   void f();
};
```