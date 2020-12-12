---
description: '詳細情報: コンパイラの警告 (レベル 1) C4186'
title: コンパイラの警告 (レベル 1) C4186
ms.date: 11/04/2016
f1_keywords:
- C4186
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
ms.openlocfilehash: 08ab6c490c404d9dabef1d5222cd388b5db7a891
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266612"
---
# <a name="compiler-warning-level-1-c4186"></a>コンパイラの警告 (レベル 1) C4186

\#インポート属性 ' attribute ' には count 引数が必要です。無効

`#import` 属性に指定されている引数の数が正しくありません。

## <a name="example"></a>例

```cpp
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

`no_namespace` 属性は引数を受け取りません。 **rename** 属性は 2 つの引数のみを受け取ります。
