---
description: 詳細については、「コンパイラエラー C3400」を参照してください。
title: コンパイラ エラー C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: d2ed88232f88c49f72c868e7b378aa0d6ef30ac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321956"
---
# <a name="compiler-error-c3400"></a>コンパイラ エラー C3400

'constraint_1' と 'constraint_2' を含む、循環制約の依存関係です

コンパイラが循環制約を検出しました。

詳細については、「[Constraints on Generic Type Parameters (C++/CLI) (ジェネリック型パラメーターの (C++/CLI))](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3400 が生成されます。

```cpp
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```
