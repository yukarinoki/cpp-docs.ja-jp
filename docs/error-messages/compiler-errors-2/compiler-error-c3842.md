---
description: 詳細については、「コンパイラエラー C3842」を参照してください。
title: コンパイラ エラー C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: dd5cff7b4a381ca976138720d8af192d594c7836
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255419"
---
# <a name="compiler-error-c3842"></a>コンパイラ エラー C3842

WinRT またはマネージド型のメンバー関数に対する 'function': 'const' および 'volatile' 修飾子はサポートされていません

Windows ランタイムまたはマネージ型のメンバー関数では、 [const](../../cpp/const-cpp.md)および[volatile](../../cpp/volatile-cpp.md)はサポートされていません。

次の例では C3842 が生成されます。

```cpp
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```
