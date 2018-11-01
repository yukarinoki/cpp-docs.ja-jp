---
title: コンパイラ エラー C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 0494961b47e99ce1f3e559302aff56278098a912
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591634"
---
# <a name="compiler-error-c3075"></a>コンパイラ エラー C3075

'instance': 参照型 'type' のインスタンスを値型に埋め込むことはできません

値型に参照型のインスタンスを含めることはできません。

詳細については、次を参照してください。[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)します。

## <a name="example"></a>例

次の例では C3075 が生成されます。

```
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```