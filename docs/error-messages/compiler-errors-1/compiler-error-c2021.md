---
title: コンパイラ エラー C2021 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31169c59ba9731d8eda52f22644294b8bb680bf2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101995"
---
# <a name="compiler-error-c2021"></a>コンパイラ エラー C2021

'character' でなく指数の値が必要です

浮動小数点定数の指数として使用される文字は、有効な数値ではありません。 指数が範囲内を使用してください。

## <a name="example"></a>例

次の例では、C2021 が生成されます。

```
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>例

考えられる解決方法:

```
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```