---
description: 詳細については、「コンパイラエラー C2931」を参照してください。
title: コンパイラ エラー C2931
ms.date: 11/04/2016
f1_keywords:
- C2931
helpviewer_keywords:
- C2931
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
ms.openlocfilehash: a4d659a0529fa80affc6749d150b9a567d015d90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320332"
---
# <a name="compiler-error-c2931"></a>コンパイラ エラー C2931

'class': type-class-id が 'identifier' のメンバー関数として再定義されています

ジェネリック クラスまたはテンプレート クラスは、別のクラスのメンバー関数として使用できません。

このエラーは、中かっこが正しく一致していない場合に発生することがあります。

次の例では C2931 が生成されます。

```cpp
// C2931.cpp
// compile with: /c
template<class T>
struct TC { };
struct MyStruct {
   void TC<int>();   // C2931
};

struct TC2 { };
struct MyStruct2 {
   void TC2();
};
```

C2931 は、ジェネリックを使用する場合にも発生することがあります。

```cpp
// C2931b.cpp
// compile with: /clr /c
generic<class T> ref struct GC {};
struct MyStruct {
   void GC<int>();   // C2931
   void GC2();   // OK
};
```
