---
title: literal (C++/CLI)
description: Literal キーワードは、Microsoft C++/CLI の状況依存のキーワードで、コンパイル時の定数を示します。
ms.date: 10/20/2020
ms.topic: reference
f1_keywords:
- literal
- literal_cpp
helpviewer_keywords:
- literal keyword [C++]
ms.openlocfilehash: 2d71a535252ba51f89407670b474a34b407eaffc
ms.sourcegitcommit: 59b7c18703d1ffd66827db0e2eeece490d3d8789
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "92337214"
---
# <a name="literal-ccli"></a>`literal` (C++/CLI)

コンパイル時にとしてマークされた変数 (データメンバー) **`literal`** **`/clr`** は、コンパイル時の定数です。 これは、C# 変数にネイティブに相当し [`const`](/dotnet/csharp/language-reference/keywords/const) ます。

## <a name="all-platforms"></a>すべてのプラットフォーム

### <a name="remarks"></a>解説

(この言語機能にはランタイムに適用される特記事項がありません。)

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>解説

(この言語機能には Windows ランタイムのみに適用される特記事項がありません。)

## <a name="common-language-runtime"></a>共通言語ランタイム

## <a name="remarks"></a>解説

としてマークされたデータメンバーは、 **`literal`** 宣言時に初期化する必要があります。 また、値は定数整数、列挙型、または文字列型である必要があります。 初期化式の型からデータメンバーの型への変換 **`literal`** では、ユーザー定義の変換は必要ありません。

実行時にフィールドに割り当てられるメモリがありません **`literal`** 。コンパイラは、その値をクラスのメタデータに挿入するだけです。 **`literal`** 値は、コンパイル時の定数として扱われます。 標準 C++ で最も近いものはです **`constexpr`** が、データメンバーを **`constexpr`** C++/cli に配置することはできません。

としてマークされている変数は、マークされたとは **`literal`** 異なり **`static const`** ます。 **`static const`** データメンバーは、メタデータで他のコンパイラに使用できるようにはなりません。 詳細については、[`static`](../cpp/storage-classes-cpp.md) および [`const`](../cpp/const-cpp.md) を参照してください。

**`literal`** は、状況依存のキーワードです。 詳細については、「 [状況依存のキーワード](context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。

## <a name="examples"></a>例

この例は、変数がを意味することを示して **`literal`** **`static`** います。

```cpp
// mcppv2_literal.cpp
// compile with: /clr
ref struct X {
   literal int i = 4;
};

int main() {
   int value = X::i;
}
```

次の例は、メタデータでのの効果を示してい **`literal`** ます。

```cpp
// mcppv2_literal2.cpp
// compile with: /clr /LD
public ref struct A {
   literal int lit = 0;
   static const int sc = 1;
};
```

メタデータでの `sc` と `lit` の違いに注目してください。`sc` には `modopt` ディレクティブが 適用され、他のコンパイラでは無視される可能性があることを意味します。

```MSIL
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x00000001)
```

```MSIL
.field public static literal int32 lit = int32(0x00000000)
```

C# で作成された次のサンプルは、前の例で作成したメタデータを参照し、変数と変数の効果を示してい **`literal`** **`static const`** ます。

```csharp
// mcppv2_literal3.cs
// compile with: /reference:mcppv2_literal2.dll
// A C# program
class B {
   public static void Main() {
      // OK
      System.Console.WriteLine(A.lit);
      System.Console.WriteLine(A.sc);

      // C# does not enforce C++ const
      A.sc = 9;
      System.Console.WriteLine(A.sc);

      // C# enforces const for a literal
      A.lit = 9;   // CS0131

      // you can assign a C++ literal variable to a C# const variable
      const int i = A.lit;
      System.Console.WriteLine(i);

      // but you cannot assign a C++ static const variable
      // to a C# const variable
      const int j = A.sc;   // CS0133
      System.Console.WriteLine(j);
   }
}
```

## <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

## <a name="see-also"></a>関連項目

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
