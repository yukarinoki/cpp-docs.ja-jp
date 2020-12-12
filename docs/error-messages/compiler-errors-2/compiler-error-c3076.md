---
description: 詳細については、「コンパイラエラー C3076」を参照してください。
title: コンパイラ エラー C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: 27fbfe27d2e8efb1abee611701fdbde8f0d3d09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320181"
---
# <a name="compiler-error-c3076"></a>コンパイラ エラー C3076

' instance ': 参照型 ' type ' のインスタンスをネイティブ型に埋め込むことはできません

ネイティブ型に CLR 型のインスタンスを含めることはできません。

詳細については、「 [参照型の C++ スタックセマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3076 が生成されます。

```cpp
// C3076.cpp
// compile with: /clr /c
ref struct U {};

struct V {
   U y;   // C3076
};

ref struct W {
   U y;   // OK
};
```
