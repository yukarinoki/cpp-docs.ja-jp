---
title: コンパイラ エラー C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: c4b4cb64da83115ab5b6a5234cda2ea3c7ba3a53
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768628"
---
# <a name="compiler-error-c3400"></a>コンパイラ エラー C3400

'constraint_1' と 'constraint_2' を含む、循環制約の依存関係です

コンパイラが循環制約を検出しました。

詳細については、[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)を参照してください。

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