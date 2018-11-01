---
title: コンパイラ エラー C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: 4eba2c9f34f1cfcaf97733f914520043ee1124bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557404"
---
# <a name="compiler-error-c3394"></a>コンパイラ エラー C3394

制約句の構文エラー: 'identifier' が見つかりましたが、型を指定しなければなりません

制約の形式が間違っています。  詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C +/cli CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)します。

## <a name="example"></a>例

次の例では C3394 が生成されます。

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```