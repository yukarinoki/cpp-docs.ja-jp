---
title: コンパイラ エラー C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: 3a0fd9c49a71f6f53d1a109378e3a6894bb68723
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175429"
---
# <a name="compiler-error-c2146"></a>コンパイラ エラー C2146

構文エラー: 識別子 'identifier' の前に ' token' がありません

予想コンパイラ`token`と`identifier`代わりにします。  以下の原因が考えられます。

1. スペルまたは大文字と小文字のエラーです。

1. 識別子の宣言で型指定子がありません。

このエラーは、入力ミスによって発生する可能性があります。 エラー [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md)通常このエラーの前にします。

## <a name="example"></a>例

次の例では、C2146 が生成されます。

```
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

## <a name="example"></a>例

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 不足している`typename`キーワード。

次の例では、Visual Studio .NET 2002 でコンパイルされますが、Visual Studio .NET 2003 では失敗します。

```
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

## <a name="example"></a>例

Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として、このエラーが表示されます。 明示的な特殊化が不要になったプライマリ テンプレートからテンプレート パラメーターを検索します。

使用`T`プライマリ テンプレートからは明示的な特殊化では許可されませんが。 Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C では有効であるコードの場合に、明示的に特殊な型で特殊化のテンプレート パラメーターのすべてのインスタンスを置き換えます。

次の例では、Visual Studio .NET でコンパイルされますが、Visual Studio .NET 2003 では失敗します。

```
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```