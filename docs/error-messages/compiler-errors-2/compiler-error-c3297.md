---
title: コンパイラ エラー C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 6df8fd3df023602f65c872dedd74da36bbbc6bd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649918"
---
# <a name="compiler-error-c3297"></a>コンパイラ エラー C3297

'constraint_2':  'constraint_1' に値の制約があるために、'constraint_1' は制約として使用できません

値クラスがシールされています。 制約が値クラスの場合は、別の制約はそこから派生できません。

詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3297 が生成されます。

```
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```