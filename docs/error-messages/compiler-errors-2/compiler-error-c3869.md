---
title: コンパイラ エラー C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 1a3d0d754557bbc811d1017ed1491181333e82dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242969"
---
# <a name="compiler-error-c3869"></a>コンパイラ エラー C3869

gcnew 制約には、空のパラメーター リスト '()' がありません。

`gcnew`空のパラメーター リストのない特殊な制約が指定されました。 参照してください[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C3869 が生成されます。

```
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```