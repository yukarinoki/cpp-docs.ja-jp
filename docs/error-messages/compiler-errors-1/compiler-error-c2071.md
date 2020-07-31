---
title: コンパイラエラー C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: cd815bf90b135f65072a56911c7c4b0f054fcfec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87210073"
---
# <a name="compiler-error-c2071"></a>コンパイラエラー C2071

'識別子' : ストレージ クラスが正しくありません。

`identifier`が無効な[ストレージクラス](../../c-language/c-storage-classes.md)で宣言されました。 1 つの識別子に複数のストレージ クラスが指定されている場合や、定義がストレージ クラスの宣言と互換性がない場合に、このエラーが発生することがあります。

この問題を解決するには、識別子の目的のストレージクラス (やなど **`static`** ) を理解 **`extern`** し、一致するように宣言を修正します。

## <a name="example"></a>例

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

## <a name="example"></a>例

次の例では C2071 エラーが生成されます。

```cpp
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```
