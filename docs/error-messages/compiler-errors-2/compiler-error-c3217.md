---
title: コンパイラ エラー C3217
ms.date: 11/04/2016
f1_keywords:
- C3217
helpviewer_keywords:
- C3217
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
ms.openlocfilehash: bcb63c7025f0addda546379947e2e1f5c3afc545
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311658"
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