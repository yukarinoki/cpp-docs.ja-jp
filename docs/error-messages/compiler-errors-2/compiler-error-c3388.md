---
title: コンパイラ エラー C3388
ms.date: 11/04/2016
f1_keywords:
- C3388
helpviewer_keywords:
- C3388
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
ms.openlocfilehash: 3b56aae115b1a1721f3f8a8688e36b25edc7f33f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328732"
---
# <a name="compiler-error-c3388"></a>コンパイラ エラー C3388

'type': 制約として使用できません。解析を続行するために 'ref class' を使用します

ジェネリック型で制約が指定されましたが、正しく指定されませんでした。 参照してください[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。

## <a name="example"></a>例

次の例では C3388 が生成されます。

```
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