---
description: 詳細については、「コンパイラエラー C3297」を参照してください。
title: コンパイラ エラー C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 39cbdfe6bbc19341c904d6bae90a71595f388400
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144600"
---
# <a name="compiler-error-c3297"></a>コンパイラ エラー C3297

'constraint_2':  'constraint_1' に値の制約があるために、'constraint_1' は制約として使用できません

値クラスがシールされています。 制約が値クラスの場合は、別の制約はそこから派生できません。

詳細については、「[Constraints on Generic Type Parameters (C++/CLI) (ジェネリック型パラメーターの (C++/CLI))](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3297 が生成されます。

```cpp
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```
