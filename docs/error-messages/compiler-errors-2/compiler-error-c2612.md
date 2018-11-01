---
title: コンパイラ エラー C2612
ms.date: 11/04/2016
f1_keywords:
- C2612
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
ms.openlocfilehash: b2d4888c1be39c4f48f0ca674426c7af612b9bb7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612161"
---
# <a name="compiler-error-c2612"></a>コンパイラ エラー C2612

末尾の 'char' ベース/メンバー初期化子リストについています。

最後のベースまたは初期化子リスト内のメンバーの後に文字が表示されます。

次の例では、C2612 が生成されます。

```
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```