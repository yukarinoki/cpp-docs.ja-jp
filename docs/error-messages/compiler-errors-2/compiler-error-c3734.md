---
description: 詳細については、「コンパイラエラー C3734」を参照してください。
title: コンパイラ エラー C3734
ms.date: 11/04/2016
f1_keywords:
- C3734
helpviewer_keywords:
- C3734
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
ms.openlocfilehash: f24c81c06a0e140f7970e8a6fc96d90aae3780f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245006"
---
# <a name="compiler-error-c3734"></a>コンパイラ エラー C3734

'class': マネージドまたは WinRT クラスは、コクラスにすることはできません

[コクラス](../../windows/attributes/coclass.md)属性は、マネージクラスまたは WinRT クラスでは使用できません。

次の例では C3734 が生成され、その修正方法が示されています。

```cpp
// C3734.cpp
// compile with: /clr /c
[module(name="x")];

[coclass]
ref class CMyClass {   // C3734 remove the ref keyword to resolve
};
```
