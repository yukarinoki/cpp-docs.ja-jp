---
description: 詳細については、「コンパイラエラー C3896」を参照してください。
title: コンパイラエラー C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: c08a9af6d10e741b39fa2547cfbc6c04a6dd3a1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222698"
---
# <a name="compiler-error-c3896"></a>コンパイラエラー C3896

' member ': 不適切な初期化子です。このリテラルデータメンバーは ' nullptr ' でのみ初期化できます

[リテラル](../../extensions/literal-cpp-component-extensions.md)データメンバーが正しく初期化されませんでした。  詳細については、 [nullptr](../../extensions/nullptr-cpp-component-extensions.md) を参照してください。

次の例では、C3896 が生成されます。

```cpp
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```
