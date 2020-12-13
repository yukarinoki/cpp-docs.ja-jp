---
description: 詳細については、「コンパイラエラー C2758」を参照してください。
title: コンパイラエラー C2758
ms.date: 11/04/2016
f1_keywords:
- C2758
helpviewer_keywords:
- C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
ms.openlocfilehash: 28ca42a5dc62ad17fef59ca129092f791a12a39f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336175"
---
# <a name="compiler-error-c2758"></a>コンパイラエラー C2758

'member': 参照型のメンバーは初期化する必要があります

初期化子リスト内の参照型のメンバーがコンストラクターによって初期化されていない場合、コンパイラ エラー C2758 が発生します。 コンパイラはそのメンバーを未定義のままにします。 参照型のメンバー変数は、コンストラクターの初期化リストで宣言されるか値を指定されるときに初期化する必要があります。

次の例では C2758 エラーが生成されます。

```cpp
// C2758.cpp
// Compile by using: cl /W3 /c C2758.cpp
struct A {
   const int i;

   A(int n) { };   // C2758
   // try the following line instead
   // A(int n) : i{n} {};
};
```
