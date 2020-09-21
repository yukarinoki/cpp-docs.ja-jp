---
title: コンパイラエラー C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 7619d968379bfc35e98bd87071b75296d10c382c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743283"
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
