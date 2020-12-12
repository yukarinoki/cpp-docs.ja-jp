---
description: 詳細については、「コンパイラエラー C2071」を参照してください。
title: コンパイラエラー C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: ec5a08150b322ca5ce3a973a4e65d71ed410e25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323195"
---
# <a name="compiler-error-c2071"></a>コンパイラエラー C2071

'識別子' : ストレージ クラスが正しくありません。

`identifier` が無効な [ストレージクラス](../../c-language/c-storage-classes.md)で宣言されました。 1 つの識別子に複数のストレージ クラスが指定されている場合や、定義がストレージ クラスの宣言と互換性がない場合に、このエラーが発生することがあります。

この問題を解決するには、識別子の目的のストレージクラス (やなど **`static`** ) を理解 **`extern`** し、一致するように宣言を修正します。

## <a name="examples"></a>例

次の例では C2071 エラーが生成されます。

```cpp
// C2071.cpp
// compile with: /c
struct C {
   extern int i;   // C2071
};
struct D {
   int i;   // OK, no extern on an automatic
};
```

次の例では C2071 エラーが生成されます。

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
