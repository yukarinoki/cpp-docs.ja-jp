---
description: 詳細については、「コンパイラエラー C3226」を参照してください。
title: コンパイラ エラー C3226
ms.date: 11/04/2016
f1_keywords:
- C3226
helpviewer_keywords:
- C3226
ms.assetid: 636106ca-6f4e-4303-a6a0-8803221ec67d
ms.openlocfilehash: f6c050f4e4c41e9ed5574c56fcc8067759cc172b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304195"
---
# <a name="compiler-error-c3226"></a>コンパイラ エラー C3226

テンプレート宣言は、ジェネリック宣言の内部では使用できません

ジェネリック クラス内部のジェネリック宣言を使用します。

次の例では C3226 が生成されます。

```cpp
// C3226.cpp
// compile with: /clr
generic <class T>
ref class C {
   template <class T1>   // C3226
   ref struct S1 {};
};
```

次の例では、考えられる解決策を示しています。

```cpp
// C3226b.cpp
// compile with: /clr /c
generic <class T>
ref class C {
   generic <class T1>
   ref struct S1 {};
};
```
