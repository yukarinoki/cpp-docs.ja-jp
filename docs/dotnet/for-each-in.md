---
title: for each、in
description: For each の C++/CLI は、ステートメントの説明と例を示しています。
ms.date: 09/25/2020
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: 7f228a773dfcbe791e26ea3e1bd8cfba7f3ab028
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413920"
---
# <a name="for-each-in"></a>for each、in

配列またはコレクションを反復処理します。 この非標準のキーワードは、C++/CLI プロジェクトと C++ ネイティブ プロジェクトの両方で使用できます。 ただし、使用しないことをお勧めします。 代わりに、標準 [の範囲ベースの For ステートメント (C++)](../cpp/range-based-for-statement-cpp.md) を使用することを検討してください。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="syntax"></a>構文

> **for each (** *式***の***型**識別子* **) {**\
> &nbsp;&nbsp;&nbsp;&nbsp;*命令*\
> **}**

### <a name="parameters"></a>パラメーター

*type*<br/>
`identifier` の型。

*identifier*<br/>
コレクション要素を表す繰り返し変数。  `identifier`が[追跡参照演算子](../extensions/tracking-reference-operator-cpp-component-extensions.md)の場合は、要素を変更できます。

*式 (expression)*<br/>
配列式またはコレクション。 コレクション要素は、コンパイラが `identifier` 型に変換できるようにする必要があります。

*命令*<br/>
実行する 1 つ以上のステートメントを指定します。

### <a name="remarks"></a>解説

コレクションを反復処理するために、`for each` ステートメントを使用します。 コレクション内の要素は変更できますが、要素を追加または削除することはできません。

*ステートメント*は、配列またはコレクション内の各要素に対して実行されます。 コレクション内の全要素に対する繰り返しが完了すると、制御は、`for each` ブロックに続くステートメントに移動します。

`for each` および `in` は、 [状況依存のキーワード](../extensions/context-sensitive-keywords-cpp-component-extensions.md)です。

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/ZW**

### <a name="example"></a>例

この例では、`for each` を使用して文字列を反復処理する方法を示します。

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>解説

CLR 構文は、次の場合を除き、 **すべてのランタイム** 構文と同じです。

*式 (expression)*<br/>
マネージド配列式またはコレクション。 コレクション要素は、コンパイラがから識別子型に変換できるようにする必要があり <xref:System.Object> ます。 *identifier*

*式* は、、、またはを実装する型に評価されます。この型は <xref:System.Collections.IEnumerable> 、 <xref:System.Collections.Generic.IEnumerable%601> `GetEnumerator` <xref:System.Collections.IEnumerator> で定義されているすべてのメソッドを実装または宣言する型を返すメソッドを定義 `IEnumerator` します。

### <a name="requirements"></a>必要条件

コンパイラ オプション: **/clr**

### <a name="example"></a>例

この例では、`for each` を使用して文字列を反復処理する方法を示します。

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

```Output
abcd

Testing
```

## <a name="see-also"></a>関連項目

[ランタイムプラットフォームのコンポーネント拡張](../extensions/component-extensions-for-runtime-platforms.md)\
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
