---
title: コンパイラ エラー C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: 70d23e22780b6efc8220675655d8ed095ca50bab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557379"
---
# <a name="compiler-error-c3400"></a>コンパイラ エラー C3400

'constraint_1' と 'constraint_2' を含む、循環制約の依存関係です

コンパイラが循環制約を検出しました。

詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3400 が生成されます。

```
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```