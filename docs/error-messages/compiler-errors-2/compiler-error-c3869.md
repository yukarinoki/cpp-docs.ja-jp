---
title: コンパイラ エラー C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 1edc90c074389d6a666d3f01f6f7be424347f51a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428133"
---
# <a name="compiler-error-c3869"></a>コンパイラ エラー C3869

gcnew 制約には、空のパラメーター リスト '()' がありません。

`gcnew`空のパラメーター リストのない特殊な制約が指定されました。 参照してください[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)詳細についてはします。

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