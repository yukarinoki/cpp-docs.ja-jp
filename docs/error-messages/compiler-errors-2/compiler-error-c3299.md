---
description: 詳細については、「コンパイラエラー C3299」を参照してください。
title: コンパイラ エラー C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: ab86a675eb13b975943130802ae98679dbc1cbb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337411"
---
# <a name="compiler-error-c3299"></a>コンパイラ エラー C3299

'member_function': 制約を指定できません。それらは基本メソッドから継承されています

汎用的なメンバー関数をオーバーライドする場合は、制約句を指定できません (制約を繰り返すことは、制約が継承されないことを意味します)。

オーバーライドするジェネリック関数の制約句が継承されます。

詳細については、「[Constraints on Generic Type Parameters (C++/CLI) (ジェネリック型パラメーターの (C++/CLI))](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では C3299 が生成されます。

```cpp
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```
