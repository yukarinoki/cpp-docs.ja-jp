---
title: コンパイラ エラー C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: edfab092c82f9dc1d4b9dfe5d21daa2b2ab98d08
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385863"
---
# <a name="compiler-error-c2581"></a>コンパイラ エラー C2581

'type' : static 'operator =' function is illegal

割り当て (`=`) 演算子が正しくとして宣言されて`static`します。 代入演算子にすることはできません`static`します。 詳細については、次を参照してください。[ユーザー定義演算子 (C +/cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)します。

## <a name="example"></a>例

次の例では、C2581 が生成されます。

```
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```