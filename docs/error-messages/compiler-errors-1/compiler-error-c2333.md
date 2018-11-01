---
title: コンパイラ エラー C2333
ms.date: 11/04/2016
f1_keywords:
- C2333
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
ms.openlocfilehash: e9119a8375a276a59cbf3a6db9541f6ccaef5122
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432634"
---
# <a name="compiler-error-c2333"></a>コンパイラ エラー C2333

'function': 関数の宣言でのエラー関数本体をスキップしています

このエラーは、クラス内で定義されているメンバー関数用の別のエラーの後に発生します。

次の例では、C2333 が生成されます。

```
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```