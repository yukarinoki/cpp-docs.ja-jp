---
description: 詳細については、「コンパイラエラー C3388」を参照してください。
title: コンパイラ エラー C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 0acc4729b5b6de61476bc134b9ef7f79bb9e86e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285527"
---
# <a name="compiler-error-c3388"></a>コンパイラ エラー C3388

'type': 制約として使用できません。解析を続行するために 'ref class' を使用します

ジェネリック型で制約が指定されましたが、正しく指定されませんでした。 詳細については、「 [ジェネリック型パラメーターの制約 (C++/cli)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3388 が生成されます。

```cpp
// C3388.cpp
// compile with: /clr /c
interface class AA {};

generic <class T>
where T : interface class   // C3388
ref class C {};

// OK
generic <class T>
where T : AA
ref class D {};
```
