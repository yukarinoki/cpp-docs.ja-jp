---
title: コンパイラ エラー C2143
ms.date: 11/04/2016
f1_keywords:
- C2143
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
ms.openlocfilehash: 310083a650f842c6c0f0912efe1ceddb66c4fd6f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214751"
---
# <a name="compiler-error-c2143"></a>コンパイラ エラー C2143

構文エラー: ' token2 ' の前に ' token1 ' がありません

コンパイラでは、特定のトークン (つまり、空白以外の言語要素) が必要ですが、代わりに別のトークンが見つかりました。

[C++ 言語リファレンス](../../cpp/cpp-language-reference.md)を調べて、コードが構文的に間違っている箇所を特定します。 コンパイラは、問題の原因となった行が検出された後にこのエラーを報告することがあるため、エラーの前にある数行のコードを確認してください。

C2143 は、さまざまな状況で発生する可能性があります。

これは、 `::` `->` `.` **`template`** 次の例のように、名前 (、、および) を修飾できる演算子の後にキーワードを指定する必要がある場合に発生することがあります。

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143
    {
    };
};
```

既定では、C++ はがテンプレートではないことを前提としています。したがって、 `Ty::PutFuncType` 次の `<` は小なり記号として解釈されます。  `PutFuncType`山かっこを正しく解析できるように、コンパイラにテンプレートであることを明示的に通知する必要があります。 このエラーを修正するには、次 **`template`** に示すように、依存する型の名前にキーワードを使用します。

```cpp
class MyClass
{
    template<class Ty, typename PropTy>
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct
    {
    };
};
```

C2143 は、 **/clr**が使用され、ディレクティブに構文エラーがある場合に発生する可能性があり **`using`** ます。

```cpp
// C2143a.cpp
// compile with: /clr /c
using namespace System.Reflection;   // C2143
using namespace System::Reflection;
```

また、 **/clr**を使用せずに CLR 構文を使用してソースコードファイルをコンパイルしようとした場合にも発生することがあります。

```cpp
// C2143b.cpp
ref struct A {   // C2143 error compile with /clr
   void Test() {}
};

int main() {
   A a;
   a.Test();
}
```

ステートメントの後に続く空白以外の最初の文字は、 **`if`** 左かっこでなければなりません。 コンパイラは、他のものを変換できません。

```cpp
// C2143c.cpp
int main() {
   int j = 0;

   // OK
   if (j < 25)
      ;

   if (j < 25)   // C2143
}
```

C2143 は、エラーが検出された行、または上記のいずれかの行で、右中かっこ、かっこ、またはセミコロンが見つからない場合に発生する可能性があります。

```cpp
// C2143d.cpp
// compile with: /c
class X {
   int member1;
   int member2   // C2143
} x;
```

または、クラス宣言に無効なタグがある場合は、次のようになります。

```cpp
// C2143e.cpp
class X {
   int member;
} x;

class + {};   // C2143 + is an invalid tag name
class ValidName {};   // OK
```

または、ラベルがステートメントにアタッチされていない場合。 たとえば、複合ステートメントの末尾にラベルを単独で配置する必要がある場合は、null ステートメントにアタッチします。

```cpp
// C2143f.cpp
// compile with: /c
void func1() {
   // OK
   end1:
      ;

   end2:   // C2143
}
```

このエラーは、C++ 標準ライブラリの型に対して非修飾呼び出しが行われた場合に発生する可能性があります。

```cpp
// C2143g.cpp
// compile with: /EHsc /c
#include <vector>
static vector<char> bad;   // C2143
static std::vector<char> good;   // OK
```

または、不足しているキーワードがあり **`typename`** ます。

```cpp
// C2143h.cpp
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};
template <typename T>
X<T>::Y X<T>::memFunc() {   // C2143
// try the following line instead
// typename X<T>::Y X<T>::memFunc() {
   return Y();
}
```

または、明示的なインスタンス化を定義しようとすると、次のようになります。

```cpp
// C2143i.cpp
// compile with: /EHsc /c
// template definition
template <class T>
void PrintType(T i, T j) {}

template void PrintType(float i, float j){}   // C2143
template void PrintType(float i, float j);   // OK
```

C プログラムでは、変数は関数の先頭で宣言する必要があり、関数が宣言以外の命令を実行した後に宣言することはできません。

```C
// C2143j.c
int main()
{
    int i = 0;
    i++;
    int j = 0; // C2143
}
```
