---
description: 詳細については、「コンパイラエラー C2386」を参照してください。
title: コンパイラ エラー C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 65dca1cf052cab1292f6f594a316536a5097a032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204096"
---
# <a name="compiler-error-c2386"></a>コンパイラ エラー C2386

'symbol' : この名前のシンボルがカレント スコープ内に既に存在します。

名前空間エイリアスを作成しようとしましたが、選択んだ名前が既に存在します。

次の例では C2386 が生成されます。

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
