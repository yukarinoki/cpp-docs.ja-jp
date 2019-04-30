---
title: コンパイラ エラー C2898
ms.date: 11/04/2016
f1_keywords:
- C2898
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
ms.openlocfilehash: 14cef7e23e48f2b5caf4fae12cac511c58ba1f1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378831"
---
# <a name="compiler-error-c2898"></a>コンパイラ エラー C2898

'declaration': メンバー関数テンプレートを仮想にすることはできません

次の例では、C2898 が生成されます。

```
// C2898.cpp
// compile with: /c
class X {
public:
   template<typename T> virtual void f(T t) {}   // C2898
};
```