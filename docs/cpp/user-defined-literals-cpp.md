---
title: ユーザー定義リテラル (C++)
description: 標準 C++ でのユーザー定義リテラルの目的と使用方法について説明します。
ms.date: 02/10/2020
ms.assetid: ff4a5bec-f795-4705-a2c0-53788fd57609
ms.openlocfilehash: 21ed3db84f057131b0404d5f950a4419cb753070
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227050"
---
# <a name="user-defined-literals"></a>ユーザー定義リテラル

C++ のリテラルには、整数、文字、浮動小数点、文字列、ブール値、およびポインターの6つの主なカテゴリがあります。 C++ 11 以降では、これらのカテゴリに基づいて独自のリテラルを定義することで、一般的な表現の構文のショートカットを提供し、タイプセーフを向上させることができます。 たとえば、クラスがあるとし `Distance` ます。 キロメートルの場合はリテラルを、マイルには別のリテラルを定義し、ユーザーに `auto d = 42.0_km` はまたはを書き込んで測定単位を明示的に指定することをお勧めし `auto d = 42.0_mi` ます。 ユーザー定義リテラルには、パフォーマンス上の利点や欠点はありません。これらは主に、便宜上、またはコンパイル時の型推論に使用されます。 標準ライブラリには、の場合は、、の場合は、 `std::string` `std::complex` ヘッダーの時間および期間操作の単位に対してユーザー定義リテラルがあり \<chrono> ます。

```cpp
Distance d = 36.0_mi + 42.0_km;         // Custom UDL (see below)
std::string str = "hello"s + "World"s;  // Standard Library <string> UDL
complex<double> num =
   (2.0 + 3.01i) * (5.0 + 4.3i);        // Standard Library <complex> UDL
auto duration = 15ms + 42h;             // Standard Library <chrono> UDLs
```

## <a name="user-defined-literal-operator-signatures"></a>ユーザー定義リテラル演算子のシグネチャ

ユーザー定義リテラルを実装するには、次のいずれかの形式の名前空間スコープで**演算子 ""** を定義します。

```cpp
ReturnType operator "" _a(unsigned long long int);   // Literal operator for user-defined INTEGRAL literal
ReturnType operator "" _b(long double);              // Literal operator for user-defined FLOATING literal
ReturnType operator "" _c(char);                     // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _d(wchar_t);                  // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _e(char16_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _f(char32_t);                 // Literal operator for user-defined CHARACTER literal
ReturnType operator "" _g(const char*, size_t);      // Literal operator for user-defined STRING literal
ReturnType operator "" _h(const wchar_t*, size_t);   // Literal operator for user-defined STRING literal
ReturnType operator "" _i(const char16_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _g(const char32_t*, size_t);  // Literal operator for user-defined STRING literal
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

前の例では、演算子の名前は任意の名前を指定できるプレース ホルダーです。ただし、先頭にアンダー スコアが必要です。 (標準ライブラリでのみ、アンダースコアなしでリテラルを定義できます)。戻り値の型は、リテラルによって実行される変換またはその他の操作をカスタマイズする場所です。 また、これらの演算子のいずれかをとして定義でき **`constexpr`** ます。

## <a name="cooked-literals"></a>cooked リテラル

ソースコードでは、ユーザー定義かどうかにかかわらず、リテラルは、基本的に `101` 、、 `54.7` 、、またはなどの英数字のシーケンスです `"hello"` **`true`** 。 コンパイラは、シーケンスを integer、float、const char 文字列などとして解釈し \* ます。 リテラル値に割り当てられている型を入力として受け入れるユーザー定義リテラルは、"調理済み"*リテラル*として非公式に知られています。 上記の `_r` と `_t` を除く演算子は、すべて cooked リテラルです。 たとえば、リテラル `42.0_km` は _b に似たシグネチャを持つ _km という名前の演算子にバインドされ、リテラル `42_km` は _a に似たシグネチャを持つ演算子にバインドされます。

次の例では、ユーザー定義リテラルが呼び出し元に入力を明記するよう求める方法を示しています。 `Distance` を構築するために、ユーザーは適切なユーザー定義リテラルを使用して、キロメートルまたはマイルを明示的に指定する必要があります。 他の方法でも同じ結果を得ることができますが、ユーザー定義のリテラルの方が、代替手段よりも詳細なものではありません。

```cpp
// UDL_Distance.cpp

#include <iostream>
#include <string>

struct Distance
{
private:
    explicit Distance(long double val) : kilometers(val)
    {}

    friend Distance operator"" _km(long double val);
    friend Distance operator"" _mi(long double val);

    long double kilometers{ 0 };
public:
    const static long double km_per_mile;
    long double get_kilometers() { return kilometers; }

    Distance operator+(Distance other)
    {
        return Distance(get_kilometers() + other.get_kilometers());
    }
};

const long double Distance::km_per_mile = 1.609344L;

Distance operator"" _km(long double val)
{
    return Distance(val);
}

Distance operator"" _mi(long double val)
{
    return Distance(val * Distance::km_per_mile);
}

int main()
{
    // Must have a decimal point to bind to the operator we defined!
    Distance d{ 402.0_km }; // construct using kilometers
    std::cout << "Kilometers in d: " << d.get_kilometers() << std::endl; // 402

    Distance d2{ 402.0_mi }; // construct using miles
    std::cout << "Kilometers in d2: " << d2.get_kilometers() << std::endl;  //646.956

    // add distances constructed with different units
    Distance d3 = 36.0_mi + 42.0_km;
    std::cout << "d3 value = " << d3.get_kilometers() << std::endl; // 99.9364

    // Distance d4(90.0); // error constructor not accessible

    std::string s;
    std::getline(std::cin, s);
    return 0;
}
```

リテラル値には10進数を使用する必要があります。 それ以外の場合、数値は整数として解釈され、型は演算子と互換性がなくなります。 浮動小数点入力の場合、型はである必要があり、整数型の場合はである必要があり **`long double`** **`long long`** ます。

## <a name="raw-literals"></a>未加工リテラル

未加工のユーザー定義リテラルでは、定義する演算子は、リテラルを char 値のシーケンスとして受け入れます。 このシーケンスは、数値や文字列などの型として解釈することができます。 このページで前述した演算子の一覧では、`_r` と `_t` を使用して未加工リテラルを定義することができます。

```cpp
ReturnType operator "" _r(const char*);              // Raw literal operator
template<char...> ReturnType operator "" _t();       // Literal operator template
```

未加工リテラルを使用して、コンパイラの通常の動作とは異なる入力シーケンスのカスタムの解釈を指定できます。 たとえば、シーケンス `4.75987` を、IEEE 754 浮動小数点型ではなく、カスタム 10 進数型に変換するリテラルを定義できます。 加工されたリテラルなどの未加工リテラルは、入力シーケンスのコンパイル時検証にも使用できます。

### <a name="example-limitations-of-raw-literals"></a>例: 未加工リテラルの制限事項

未加工リテラルの演算子とリテラルの演算子のテンプレートは、次の例に示すように、整数および浮動小数点のユーザー定義リテラルに対してのみ動作します。

```cpp
#include <cstddef>
#include <cstdio>

// Literal operator for user-defined INTEGRAL literal
void operator "" _dump(unsigned long long int lit)
{
    printf("operator \"\" _dump(unsigned long long int) : ===>%llu<===\n", lit);
};

// Literal operator for user-defined FLOATING literal
void operator "" _dump(long double lit)
{
    printf("operator \"\" _dump(long double)            : ===>%Lf<===\n",  lit);
};

// Literal operator for user-defined CHARACTER literal
void operator "" _dump(char lit)
{
    printf("operator \"\" _dump(char)                   : ===>%c<===\n",   lit);
};

void operator "" _dump(wchar_t lit)
{
    printf("operator \"\" _dump(wchar_t)                : ===>%d<===\n",   lit);
};

void operator "" _dump(char16_t lit)
{
    printf("operator \"\" _dump(char16_t)               : ===>%d<===\n",   lit);
};

void operator "" _dump(char32_t lit)
{
    printf("operator \"\" _dump(char32_t)               : ===>%d<===\n",   lit);
};

// Literal operator for user-defined STRING literal
void operator "" _dump(const     char* lit, size_t)
{
    printf("operator \"\" _dump(const     char*, size_t): ===>%s<===\n",   lit);
};

void operator "" _dump(const  wchar_t* lit, size_t)
{
    printf("operator \"\" _dump(const  wchar_t*, size_t): ===>%ls<===\n",  lit);
};

void operator "" _dump(const char16_t* lit, size_t)
{
    printf("operator \"\" _dump(const char16_t*, size_t):\n"                  );
};

void operator "" _dump(const char32_t* lit, size_t)
{
    printf("operator \"\" _dump(const char32_t*, size_t):\n"                  );
};

// Raw literal operator
void operator "" _dump_raw(const char* lit)
{
    printf("operator \"\" _dump_raw(const char*)        : ===>%s<===\n",   lit);
};

template<char...> void operator "" _dump_template();       // Literal operator template

int main(int argc, const char* argv[])
{
    42_dump;
    3.1415926_dump;
    3.14e+25_dump;
     'A'_dump;
    L'B'_dump;
    u'C'_dump;
    U'D'_dump;
      "Hello World"_dump;
     L"Wide String"_dump;
    u8"UTF-8 String"_dump;
     u"UTF-16 String"_dump;
     U"UTF-32 String"_dump;
    42_dump_raw;
    3.1415926_dump_raw;
    3.14e+25_dump_raw;

    // There is no raw literal operator or literal operator template support on these types:
    //  'A'_dump_raw;
    // L'B'_dump_raw;
    // u'C'_dump_raw;
    // U'D'_dump_raw;
    //   "Hello World"_dump_raw;
    //  L"Wide String"_dump_raw;
    // u8"UTF-8 String"_dump_raw;
    //  u"UTF-16 String"_dump_raw;
    //  U"UTF-32 String"_dump_raw;
}
```

```Output
operator "" _dump(unsigned long long int) : ===>42<===
operator "" _dump(long double)            : ===>3.141593<===
operator "" _dump(long double)            : ===>31399999999999998506827776.000000<===
operator "" _dump(char)                   : ===>A<===
operator "" _dump(wchar_t)                : ===>66<===
operator "" _dump(char16_t)               : ===>67<===
operator "" _dump(char32_t)               : ===>68<===
operator "" _dump(const     char*, size_t): ===>Hello World<===
operator "" _dump(const  wchar_t*, size_t): ===>Wide String<===
operator "" _dump(const     char*, size_t): ===>UTF-8 String<===
operator "" _dump(const char16_t*, size_t):
operator "" _dump(const char32_t*, size_t):
operator "" _dump_raw(const char*)        : ===>42<===
operator "" _dump_raw(const char*)        : ===>3.1415926<===
operator "" _dump_raw(const char*)        : ===>3.14e+25<===
```
