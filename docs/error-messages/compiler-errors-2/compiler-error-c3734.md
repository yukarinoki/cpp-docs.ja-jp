---
title: コンパイラ エラー C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: 78b3d1a57d358eb11ba2f01ec184c5487a578228
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648319"
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
