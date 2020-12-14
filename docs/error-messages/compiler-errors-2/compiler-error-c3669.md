---
description: 詳細については、「コンパイラエラー C3669」を参照してください。
title: コンパイラ エラー C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: b746c64af06178caf1006417f61c5f1e853cb67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228951"
---
# <a name="compiler-error-c3669"></a>コンパイラ エラー C3669

' member ': オーバーライド指定子 ' override ' は、静的メンバー関数またはコンストラクターでは使用できません

オーバーライドが正しく指定されませんでした。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3669 が生成されます。

```cpp
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```
