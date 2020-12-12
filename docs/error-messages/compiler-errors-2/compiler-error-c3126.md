---
description: 詳細については、「コンパイラエラー C3126」を参照してください。
title: コンパイラエラー C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 7084359ae0be412ccb36e9a634cc72848f1c8daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345460"
---
# <a name="compiler-error-c3126"></a>コンパイラエラー C3126

マネージド型 ' type ' 内で共用体 ' union ' を定義することはできません

共用体はマネージド型の内部では定義できません。

次の例では、C3126 が生成されます。

```cpp
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```
