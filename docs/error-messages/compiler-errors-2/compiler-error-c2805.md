---
title: コンパイラ エラー C2805
ms.date: 11/04/2016
f1_keywords:
- C2805
helpviewer_keywords:
- C2805
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
ms.openlocfilehash: b0b3c0d4291787fb0b5664baa9159c84c8549dfd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62282072"
---
# <a name="compiler-error-c2805"></a>コンパイラ エラー C2805

二項 'operator 演算子' は引数が少なすぎます

二項演算子には、パラメーターがありません。

次の例では、C2805 が生成されます。

```
// C2805.cpp
// compile with: /c
class X {
public:
   X operator< ( void );   // C2805 must take one parameter
   X operator< ( X );   // OK
};
```