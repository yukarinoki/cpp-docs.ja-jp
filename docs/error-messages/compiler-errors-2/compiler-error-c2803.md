---
title: コンパイラ エラー C2803 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7885735ebad1ff90afaf4ba8eaf6dfca9f3e0ab3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027041"
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