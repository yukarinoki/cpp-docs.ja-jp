---
title: コンパイラ エラー C3347
ms.date: 11/04/2016
f1_keywords:
- C3347
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
ms.openlocfilehash: 8b1c4ea76f65b9f07a96177d2e481d1abeba0927
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300644"
---
# <a name="compiler-error-c3347"></a>コンパイラ エラー C3347

'arg': 必要な引数が属性 idl_module 内で指定されていません

[idl_module](../../windows/idl-module.md) 属性に必須の引数が渡されていません。

次の例では C3347 が生成されます。

```
// C3347.cpp
// compile with: /c
[module(name="xx")];

[idl_module(dllname="x")];    // C3347
// try the following line instead
// [idl_module(name="test", dllname="x")];
```