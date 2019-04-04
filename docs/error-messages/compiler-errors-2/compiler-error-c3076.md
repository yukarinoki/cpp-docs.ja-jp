---
title: コンパイラ エラー C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: ac9afdfc11a13dd667b06289c73332593a4d884e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456356"
---
# <a name="compiler-error-c3076"></a>コンパイラ エラー C3076

'instance': 参照型 'type' のインスタンスをネイティブ型に埋め込むことはできません

ネイティブ型には、CLR 型のインスタンスを含めることはできません。

詳細については、[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)を参照してください。

## <a name="example"></a>例

次の例では、C3076 が生成されます。

```
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