---
title: コンパイラの警告 (レベル 1) C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: fa5f0c3d3d409384b7cdc3c8a9cbe884732cbf8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646577"
---
# <a name="compiler-warning-level-1-c4186"></a>コンパイラの警告 (レベル 1) C4186

\#インポート属性 'attribute' には、数の引数が必要です。無視されます。

`#import` 属性に指定されている引数の数が正しくありません。

## <a name="example"></a>例

```
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` 属性は引数を受け取りません。 **rename** 属性は 2 つの引数のみを受け取ります。