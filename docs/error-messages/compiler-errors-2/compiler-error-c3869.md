---
description: 詳細については、「コンパイラエラー C3869」を参照してください。
title: コンパイラ エラー C3869
ms.date: 11/04/2016
f1_keywords:
- C3869
helpviewer_keywords:
- C3869
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
ms.openlocfilehash: 8b5bcd59bfeb5407edcfbea6217212dfc44c6643
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222789"
---
# <a name="compiler-error-c3869"></a>コンパイラ エラー C3869

gcnew 制約に空のパラメーターリスト ' () ' がありません

**`gcnew`** 空のパラメーターリストを指定せずに特殊な制約が指定されました。 詳細については、「 [ジェネリック型パラメーターの制約 (C++/cli)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C3869 が生成されます。

```cpp
// C3869.cpp
// compile with: /c /clr
using namespace System;
generic <typename T>
where T : gcnew   // C3869
// try the following line instead
// where T : gcnew()
ref class List {};
```
