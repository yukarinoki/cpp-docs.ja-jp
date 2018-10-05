---
title: コンパイラ エラー C3455 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3455
dev_langs:
- C++
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a10c91f34cd00b8524a047131e9a39b901c83fce
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788592"
---
# <a name="compiler-error-c3455"></a>コンパイラ エラー C3455

'attribute': どの属性コンストラクターも引数に一致しませんでした

無効な値が属性の宣言に使用されました。  参照してください[属性](../../windows/attributes/attribute.md)詳細についてはします。

## <a name="example"></a>例

次の例では C3455 が生成されます。

```
// C3455.cpp
// compile with: /clr /c
using namespace System;

[attribute("MyAt")]   // C3455
// try the following line instead
// [attribute(All)]
ref struct MyAttr {
   MyAttr() {}
};
```