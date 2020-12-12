---
description: 詳細については、「コンパイラエラー C3075」を参照してください。
title: コンパイラ エラー C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 68169ade5e9de13b618fe6d90936cbe887690775
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320224"
---
# <a name="compiler-error-c3075"></a>コンパイラ エラー C3075

'instance': 参照型 'type' のインスタンスを値型に埋め込むことはできません

値型に参照型のインスタンスを含めることはできません。

詳細については、「 [参照型の C++ スタックセマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。

## <a name="example"></a>例

次の例では C3075 が生成されます。

```cpp
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
