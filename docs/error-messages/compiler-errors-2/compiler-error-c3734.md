---
title: コンパイラ エラー C3734 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3734
dev_langs:
- C++
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d304b3853986b54f9844f9e4968f7bb7d6a8af5a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072746"
---
# <a name="compiler-error-c3734"></a>コンパイラ エラー C3734

'class': マネージドまたは WinRT クラスは、コクラスにすることはできません

[コクラス](../../windows/coclass.md)属性では使用できませんマネージまたは WinRT クラス。

次の例では C3734 が生成され、その修正方法が示されています。

```
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
