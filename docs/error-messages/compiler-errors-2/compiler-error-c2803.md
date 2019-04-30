---
title: コンパイラ エラー C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d20b8dde9f4134273adcba0f947f685f7ce7d213
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408525"
---
# <a name="compiler-error-c2803"></a>コンパイラ エラー C2803

'operator 演算子' がクラス型の仮パラメーターを少なくとも 1 つあります。

オーバー ロードされた演算子には、クラス型のパラメーターが不足しています。

参照 (ポインターが参照を使用していない) または値を書き込みを可能にするには少なくとも 1 つのパラメーターを渡す必要がある"、< b"(の型クラス A と b)。

両方のパラメーターがポインターの場合、ポインター アドレスの純粋な比較になり、ユーザー定義の変換は使用しません。

次の例では、C2803 が生成されます。

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```