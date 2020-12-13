---
description: 詳細については、「コンパイラエラー C2523」を参照してください。
title: コンパイラ エラー C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: c9907742903cf4c13364d6ac63bb561b52e02232
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151165"
---
# <a name="compiler-error-c2523"></a>コンパイラ エラー C2523

' class:: ~ identifier ': デストラクターまたはファイナライザーのタグが一致しません。

デストラクターの名前は、クラス名の前にチルダ () を付ける必要があり `~` ます。 コンストラクターとデストラクターは、クラスと同じ名前を持つ唯一のメンバーです。

次の例では、C2523 が生成されます。

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```
