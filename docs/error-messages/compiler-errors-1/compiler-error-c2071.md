---
title: コンパイラ エラー C2071
ms.date: 11/04/2016
f1_keywords:
- C2071
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
ms.openlocfilehash: 95344b5ef675f566f433dfeaed9dee5c38ef77d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598277"
---
# <a name="compiler-error-c2071"></a>コンパイラ エラー C2071

'識別子' : ストレージ クラスが正しくありません。

`identifier` 無効な状態で宣言されました[ストレージ クラス](../../c-language/c-storage-classes.md)します。 1 つの識別子に複数のストレージ クラスが指定されている場合や、定義がストレージ クラスの宣言と互換性がない場合に、このエラーが発生することがあります。

この問題を解決するには、識別子の目的の記憶域クラスを理解する — たとえば、`static`または`extern`— と一致するように宣言を修正します。

## <a name="example"></a>例

次の例では C2071 エラーが生成されます。

```
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

```
// C2071_b.cpp
// compile with: /c
typedef int x(int i) { return i; }   // C2071
typedef int (x)(int);   // OK, no local definition in typedef
```