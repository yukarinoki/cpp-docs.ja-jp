---
description: 詳細については、「コンパイラエラー C3666」を参照してください。
title: コンパイラ エラー C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 245fd061a7a1ce7b9b3e25ae76e6b15ec9428145
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134265"
---
# <a name="compiler-error-c3666"></a>コンパイラ エラー C3666

' constructor ': オーバーライド指定子 ' keyword ' はコンストラクターでは使用できません

オーバーライド指定子がコンストラクターで使用されましたが、これは許可されていません。 詳細については、「 [オーバーライド指定子](../../extensions/override-specifiers-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3666 が生成されます。

```cpp
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```
