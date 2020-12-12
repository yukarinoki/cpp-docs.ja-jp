---
description: 詳細については、「コンパイラエラー C3131」を参照してください。
title: コンパイラエラー C3131
ms.date: 11/04/2016
f1_keywords:
- C3131
helpviewer_keywords:
- C3131
ms.assetid: 38f20fac-83c9-4cd9-b7b5-74ca8f650ea6
ms.openlocfilehash: 3fde5045f2c14efdac96f902e12dcea1f5118505
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177407"
---
# <a name="compiler-error-c3131"></a>コンパイラエラー C3131

プロジェクトには ' name ' プロパティを持つ ' module ' 属性が必要です

[Module](../../windows/attributes/module-cpp.md)属性には name パラメーターが必要です。

次の例では、C3131 が生成されます。

```cpp
// C3131.cpp
[emitidl];
[module];   // C3131
// try the following line instead
// [module (name="MyLib")];

[public]
typedef long int LongInt;
```
