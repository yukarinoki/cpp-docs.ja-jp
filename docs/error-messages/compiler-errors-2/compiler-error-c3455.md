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
ms.openlocfilehash: 5d26a8f3e404eaa19a102be4cb3f11350c4fe674
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089360"
---
# <a name="compiler-error-c3455"></a>コンパイラ エラー C3455

'attribute': どの属性コンストラクターも引数に一致しませんでした

無効な値が属性の宣言に使用されました。  詳細については、「 [attribute](../../windows/attribute.md) 」を参照してください。

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