---
title: コンパイラ エラー C2513
ms.date: 11/04/2016
f1_keywords:
- C2513
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
ms.openlocfilehash: 96f2ccc29eed5c1fa4e29f69d18ae6503417f211
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212723"
---
# <a name="compiler-error-c2513"></a>コンパイラ エラー C2513

' type ': ' = ' の前に変数が宣言されていません

型指定子が、変数識別子のない宣言に出現します。

次の例では、C2513 が生成されます。

```cpp
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

このエラーは、Visual Studio .NET 2003 でコンパイラ準拠作業が行われた結果として生成される場合もあります。 typedef の初期化が許可されなくなりました。 Typedef の初期化は標準では許可されておらず、コンパイラエラーが生成されるようになりました。

```cpp
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

または、を削除して、 **`typedef`** 集計初期化子リストを持つ変数を定義することもできますが、この方法は推奨されません。これは、型と同じ名前の変数を作成し、型名を非表示にするためです。
