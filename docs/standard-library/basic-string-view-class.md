---
title: basic_string_view クラス
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 0ac5e3d528881f7b1caa0a1dcdae0161a6777e57
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346940"
---
# <a name="basicstringview-class"></a>basic_string_view クラス

クラス テンプレート`basic_string_view<charT>`を受け入れるさまざまな関数の安全で効率的な方法と文字列型は無関係にそれらの型でテンプレート化される関数を使用せずに処理するために c++ 17 で追加されました。 クラスは、連続するシーケンスを文字データ、およびシーケンス内の文字数を指定する長さの所有している以外のポインターを保持します。 シーケンスが null で終わるかどうかに関する仮定は行われません。

標準ライブラリでは、要素の型に基づいていくつかの特殊化を定義します。

-  `string_view`
-  `wstring_view`
-  `u16string_view`
-  `u32string_view`

このドキュメントで"string_view"とは一般にこれらの typedef のいずれかです。

String_view では、文字列データを読み取るために必要な最小の共通のインターフェイスについて説明します。 は、基になるデータへの const のアクセスを提供しますコピーがない (を除く、`copy`関数)。 データは、任意の位置に null 値 ('\0') を含めることはできません。 オブジェクトの有効期間を制御する string_view を与えません。 基になる文字列データが有効であることを確認する呼び出し元の責任になります。

型 string_view のパラメーターを受け入れる関数がテンプレートに関数を作成するか、文字列型の特定のサブセットに関数を制限なく、任意の文字列のような型を処理できます。 唯一の要件は、string_view に文字列型からの暗黙的な変換が存在します。 すべての標準的な文字列型が同じ種類の要素を含む string_view に暗黙的に変換します。 つまり、`std::string`に変換できる、`string_view`には、`wstring_view`します。

次の例では、非テンプレート関数`f`型のパラメーターを受け取る`wstring_view`します。 型の引数と共に呼び出せる`std::wstring`、 `wchar_t*`、および`winrt::hstring`します。

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>構文

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>パラメーター

*CharType*<br/>
String_view に格納されている文字の型。 C++標準ライブラリでは、このテンプレートの特殊化の次の typedef。
- [string_view](../standard-library/string-view-typedefs.md#string_view)型の要素に対して**char**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view)の**wchar_t**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)の**char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)の**char32_t**します。

*Traits*<br/>
既定値は[char_traits](char-traits-struct.md)<*CharType*>。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_string_view](#basic_string_view)|ポイントしたり、他の文字列オブジェクトのデータのすべてまたは一部を C スタイル文字配列にするか、空を string_view を構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|**const_iterator**|読み取ることができるランダム アクセス反復子**const**要素。|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**Iterator**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**pointer**|`using pointer = value_type*;`|
|**reference**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>メンバー演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|別 string_view string_view または変換できる文字列オブジェクトを代入します。|
|[operator\[\]](#op_at)|指定したインデックス位置にある要素を返します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[at](#at)|指定した位置にある要素を const_reference を返します。|
|[back](#back)|最後の要素を const_reference を返します。|
|[begin](#begin)|最初の要素を示す定数反復子を返します。 (string_views は変更できません) です。|
|[cbegin](#cbegin)|同じ[開始](#begin)します。|
|[cend](#cend)|1 つ後ろの最後の要素を指す定数反復子を返します。|
|[copy](#copy)|最大文字数を指定したソース string_view でのインデックス位置から、ターゲット文字配列へコピーします。 (推奨されません。 _Copy_s 代わりに使用します。)|
|[_Copy_s](#_copy_s)|セキュリティで保護された CRT コピー関数。|
|[compare](#compare)|等しい場合は、または一方が他方より小さいか辞書式に判断する指定の string_view の string_view を比較します。|
|[crbegin](#crbegin)|同じ[rbegin](#rbegin)します。|
|[crend](#crend)|同じ[rend](#rend)します。|
|[data](#data)|文字シーケンスを所有している非生のポインターを返します。|
|[empty](#empty)|String_view には文字が含まれているかどうかをテストします。|
|[end](#end)|同じ[cend](#cend)します。|
|[find](#find)|指定された一連の文字に一致する部分文字列の最初の出現順方向に検索します。|
|[find_first_not_of](#find_first_not_of)|指定した string_view または変換できる文字列オブジェクトの要素ではない最初の文字を検索します。|
|[find_first_of](#find_first_of)|指定した string_view または変換できる文字列オブジェクトの任意の要素に一致する最初の文字を検索します。|
|[find_last_not_of](#find_last_not_of)|指定した string_view または変換できる文字列オブジェクトの要素ではない最後の文字を検索します。|
|[find_last_of](#find_last_of)|指定した string_view または変換できる文字列オブジェクトの要素は、最後の文字を検索します。|
|[front](#front)|最初の要素を const_reference を返します。|
|[length](#length)|現在の要素数を返します。|
|[max_size](#max_size)|String_view を含めたりする文字の最大数を返します。|
|[rbegin](#rbegin)|反転 string_view 内の最初の要素を指す定数反復子を返します。|
|[remove_prefix](#remove_prefix)|指定した要素数では、転送ポインターを移動します。|
|[remove_suffix](#remove_suffix)|指定した数の要素の後ろから開始して、ビューのサイズが減ります。|
|[rend](#rend)|1 つ後ろ反転 string_view の最後の要素を指す定数反復子を返します。|
|[rfind](#rfind)|最初に出現する位置の指定した一連の文字に一致する部分文字列の逆の順序で、string_view を検索します。|
|[size](#size)|現在の要素数を返します。|
|[substr](#substr)|指定したインデックスから始まる指定された長さの部分文字列を返します。|
|[swap](#swap)|2 つの string_views の内容と交換します。|

## <a name="remarks"></a>Remarks

関数が [max_size](#max_size) の要素よりも長いシーケンスを生成するように指示された場合、関数は [length_error](../standard-library/length-error-class.md) 型のオブジェクトをスローして長さエラーを報告します。

## <a name="requirements"></a>必要条件

[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)またはそれ以降

**ヘッダー:** \<string_view >

**名前空間:** std

## <a name="at"></a>  basic_string_view::at

指定した 0 から始まるインデックス位置の文字を const_reference を返します。

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
参照される要素のインデックス。

### <a name="return-value"></a>戻り値

パラメーターのインデックスで指定した位置にある文字に const_reference します。

### <a name="remarks"></a>Remarks

最初の要素がゼロのインデックスと、次の要素が連続した正の整数によってインデックスが作成できるようにの長さの string_view *n*が、 *n*番目の要素は、数によってインデックス付けされた*n -* 1。 **と**は異なり、無効なインデックスの例外がスロー[演算子\[\]](#op_at)します。 

一般に、お勧め**で**などのシーケンスの`std::vector`と string_view は使用しないでください。 シーケンスに渡された無効なインデックスは、論理エラーが検出され、開発時に修正する必要があります。 プログラムがそのインデックスが有効なことが特定されていない場合する必要がありますそれらをテスト、いない at() を呼び出すおよび不注意なプログラミングを防御する例外に依存します。

参照してください[basic_string_view::operator\[ \] ](#op_at)詳細についてはします。

### <a name="example"></a>例

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="back"></a>  basic_string_view::back

最後の要素を const_reference を返します。

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>戻り値

String_view の最後の要素に const_reference します。

### <a name="remarks"></a>Remarks

String_view が空の場合は、例外をスローします。

注意を string_view を変更した後、たとえば呼び出して`remove_suffix`、この関数によって返される要素が基になるデータの最後の要素ではなくなりました。

### <a name="example"></a>例

C の文字列リテラルを使用して構築されている string_view に終端の null は含まれませんため次の例では`back`'p' と '\0' を返します。

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p 
```

埋め込み null は、その他の任意の文字として扱われます。

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_view"></a>  basic_string_view::basic_string_view

String_view を構築します。

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
文字の値へのポインター。

*len*<br/>
ビューに含める文字数。

## <a name="remarks"></a>Remarks

グラフ * パラメーターを持つコンス トラクターには、string_view に終端の null は含まれませんが、入力が null で終わるものとします。

リテラルの string_view を構築することもできます。 参照してください[演算子""sv](string-view-operators.md#op_sv)します。

## <a name="begin"></a>  basic_string_view::begin

同じ[cbegin](#cbegin)します。

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>戻り値
最初の要素をアドレス指定 const_iterator を返します。

## <a name="cbegin"></a>  basic_string_view::cbegin

範囲内の最初の要素を指す const_iterator を返します。

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

A **const**最初の要素の範囲、または空の範囲の末尾の次の場所を指すランダム アクセス反復子 (空の範囲、 `cbegin() == cend()`)。

## <a name="cend"></a>  basic_string_view::cend

範囲の最後の要素の次の位置を指す const_iterator を返します。

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>戻り値

A **const**範囲の終了位置を指すランダム アクセス反復子。

### <a name="remarks"></a>Remarks

`cend` によって返された値は逆参照しないでください。

## <a name="compare"></a> basic_string_view::compare

2 つのオブジェクトが等しい場合、または一方が他方より小さいか辞書式に判断する指定された string_view (または変換できる文字列型) で大文字小文字が区別の比較を行います。 [ \<String_view > 演算子](string-view-operators.md)比較を実行するこのメンバー関数を使用します。

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>パラメーター

*strv*<br/>
この string_view と比較する string_view します。

*pos*<br/>
比較が開始されるこの string_view のインデックス。

*num*<br/>
この string_view と比較する文字の最大数。

*num2*<br/>
文字の最大数*strv*と比較します。

*オフセット*<br/>
インデックス*strv*比較が開始する位置。

*ptr*<br/>
この string_view と比較する C 文字列。

### <a name="return-value"></a>戻り値

負の値を使用している場合はこの string_view より小さい*strv*または*ptr*はゼロの 2 つの文字のシーケンスが等しい場合は正の値よりも大きい場合はこの string_view *strv*または*ptr*します。

### <a name="remarks"></a>Remarks

`compare`メンバー関数は、すべてまたは各文字のシーケンスの一部の大文字小文字の比較を実行します。 

### <a name="example"></a>例

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are" 
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are" 
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a) 
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="copy"></a>  basic_string_view::copy

最大文字数を指定したソース string_view でのインデックス位置から、ターゲット文字配列へコピーします。 セキュリティで保護された関数を使用することをお勧めします。 [basic_string_view::_Copy_s](#_copy_s)代わりにします。

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
要素のコピー先のターゲット文字配列。

*count*<br/>
コピーされる、最大でソース string_view 文字の数。

*オフセット*<br/>
コピーが作成される元のソース string_view で先頭位置。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。

### <a name="remarks"></a>Remarks

null 文字はコピーの末尾には追加されません。

## <a name="_copy_s"></a>  basic_string_view::_Copy_s

CRT のコピー関数の代わりに使用するセキュリティで保護された[コピー](#copy)します。

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>パラメーター

*dest*<br/>
要素のコピー先のターゲット文字配列。

*dest_size*<br/>
サイズ*dest*します。

_*カウント*からコピーされる、最大では、ソース文字列の文字数。

*_Off*<br/>
ソース文字列内のコピーの作成開始位置。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。

### <a name="remarks"></a>Remarks

null 文字はコピーの末尾には追加されません。

 詳細については、次を参照してください。 [c-runtime-library/security-features-in-the-crt](../c-runtime-library/security-features-in-the-crt.md)します。

## <a name="crbegin"></a>  basic_string_view::crbegin

反転 string_view 内の最初の要素を指す const_reverse_iterator を返します。

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

反転 string_view 内の最初の要素を指す const_reverse_iterator します。 

## <a name="crend"></a>  basic_string_view::crend

同じ[rend](#rend)します。 

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>戻り値

末尾の反転の string_view のいずれかを指す const_reverse_iterator を返します。

## <a name="data"></a>  basic_string_view::data

String_view の構築に使用されたオブジェクトの const の文字シーケンスを所有している非生のポインターを返します。

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>戻り値

ポインターを定数文字シーケンスの最初の要素を。

### <a name="remarks"></a>Remarks

ポインターは、文字を変更できません。

String_view 文字のシーケンスは、null 終端する必要ありません。 戻り値の型`data`null 文字が追加されないために、有効な C 文字列ではありません。 Null 文字 '\0' は型 string_view のオブジェクトの特別な意味を持たないし、その他の任意の文字と同様、string_view オブジェクトの一部にすることがあります。

## <a name="empty"></a>  basic_string_view::empty

かどうか、string_view に文字が含まれているかどうかをテストします。

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>戻り値

**true** string_view オブジェクトに文字が含まれていない場合**false**に少なくとも 1 つの文字がある場合。

### <a name="remarks"></a>Remarks

メンバー関数は等しく[サイズ](#size)() = 0。

## <a name="end"></a>  basic_string_view::end

1 つ後ろの最後の要素を指すランダム アクセス const_iterator を返します。

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>戻り値

1 つ後ろの最後の要素を指すランダム アクセス const_iterator を返します。

### <a name="remarks"></a>Remarks

`end` const_iterator がその string_view の末尾に達したかどうかをテストに使用されます。 `end` によって返された値は逆参照しないでください。

## <a name="find"></a>  basic_string_view::find

文字または文字の指定したシーケンスと一致した部分文字列の最初の出現順方向に、string_view を検索します。

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
メンバー関数が検索対象の string_view します。

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
インデックス検索の開始位置。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
文字数*ptr*、最初の文字から数えています。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="find_first_not_of"></a>  basic_string_view::find_first_not_of

指定した string_view または変換できる文字列オブジェクトの要素ではない最初の文字を検索します。

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
メンバー関数が検索対象の string_view します。

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
インデックス検索の開始位置。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
メンバー関数が検索される C 文字列で、最初の文字から数えて、文字数。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="find_first_of"></a>  basic_string_view::find_first_of

指定した string_view の任意の要素に一致する最初の文字を検索します。

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
インデックス検索の開始位置。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
メンバー関数が検索される C 文字列で、最初の文字から数えて、文字数。

*str*<br/>
メンバー関数が検索対象の string_view します。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="find_last_not_of"></a>  basic_string_view::find_last_not_of

指定した string_view の要素ではない最後の文字を検索します。

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
メンバー関数が検索対象の string_view します。

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
検索の終了位置のインデックス。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
数えて最初の文字の文字数*ptr*します。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `string_view::npos`。

## <a name="find_last_of"></a>  basic_string_view::find_last_of

指定した string_view の任意の要素に一致する最後の文字を検索します。

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
メンバー関数が検索対象の string_view します。

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
検索の終了位置のインデックス。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
メンバー関数が検索される C 文字列で、最初の文字から数えて、文字数。

### <a name="return-value"></a>戻り値

成功した場合は検索する部分文字列の最後の文字のインデックス、それ以外の場合は `npos`。

## <a name="front"></a>  basic_string_view::front

最初の要素を const_reference を返します。

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>戻り値

最初の要素に const_reference します。

### <a name="remarks"></a>Remarks

String_view が空の場合は、例外をスローします。

## <a name="length"></a> basic_string_view::length

現在の要素数を返します。

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Remarks

このメンバー関数は [size](#size) と同じです。

## <a name="max_size"></a>  basic_string_view::max_size

文字を含めることができます、string_view の最大数を返します。

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>戻り値

String_view 文字の最大数を含めることができます。

### <a name="remarks"></a>Remarks

型の例外[length_error](../standard-library/length-error-class.md)操作を超える長さの string_view を生成する場合にスローされる`max_size()`します。

## <a name="op_eq"></a>  basic_string_view::operator=

別 string_view string_view または変換できる文字列オブジェクトを代入します。

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```
### <a name="example"></a>例

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```
## <a name="op_at"></a>  basic_string_view::operator[]

指定したインデックスには、文字の const_reference を提供します。

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
参照される要素のインデックス。

### <a name="return-value"></a>戻り値

パラメーターのインデックスで指定した位置にある文字に const_reference します。

### <a name="remarks"></a>Remarks

最初の要素がゼロのインデックスと、次の要素が連続した正の整数によってインデックスが作成できるようにの長さの string_view *n*が、 *n*番目の要素は、数によってインデックス付けされた*n* - 1。

`operator[]` メンバー関数より高速[で](#at)string_view の要素への読み取りアクセスを提供するためです。

`operator[]` 引数として渡されたインデックスが有効かどうかをチェックしません。 無効なインデックスが渡される`operator[]`未定義の動作になります。

基になる文字列データが変更されたり、所有するオブジェクトによって削除された場合、返される参照を無効にすることがあります。

コンパイルするときに[\_反復子\_デバッグ\_レベル](../standard-library/iterator-debug-level.md)1 または 2 に設定するに、string_view の境界の外側の要素にアクセスしようとした場合、ランタイム エラーは発生されます。 詳細については、「 [Checked Iterators](../standard-library/checked-iterators.md)」を参照してください。

## <a name="rbegin"></a>  basic_string_view::rbegin

反転 string_view の最初の要素に定数反復子を返します。

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

対応する通常の順序の string_view の最後の要素には何をアドレス指定、反転 string_view の最初の要素をランダム アクセス反復子を返します。

### <a name="remarks"></a>Remarks

`rbegin` 反転 string_view と共に使用と同様[開始](#begin)string_view と共に使用します。 `rbegin` 下位のイテレーションを初期化するために使用できます。

## <a name="remove_prefix"></a> basic_string_view::remove_prefix

指定した要素数では、転送ポインターを移動します。

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Remarks

基になるデータに変更を残します。 N 個の要素によって string_view ポインターを前方に移動し、プライベートを設定`size`サイズ - n するデータ メンバー。

## <a name="remove_suffix"></a> basic_string_view::remove_suffix

指定した数の要素の後ろから開始して、ビューのサイズが減ります。

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Remarks

基になるデータと、ポインターのまま、そのままにします。 プライベート設定`size`サイズ - n するデータ メンバー。

## <a name="rend"></a>  basic_string_view::rend

1 つ後ろ反転 string_view の最後の要素を指す定数反復子を返します。

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>戻り値

定数は逆順ランダム アクセス反復子を指す反転 string_view の最後の要素より 1 つです。

### <a name="remarks"></a>Remarks

`rend` 反転 string_view と共に使用と同様[エンド](#end)string_view と共に使用します。 `rend` 逆順反復子の string_view の末尾に達したかどうかをテストするために使用します。 `rend` によって返された値は逆参照しないでください。

## <a name="rfind"></a>  basic_string_view::rfind

指定された一連の文字に一致する部分文字列を逆の順序で、string_view を検索します。

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*chVal*<br/>
メンバー関数が検索される文字値。

*オフセット*<br/>
インデックス検索の開始位置。

*ptr*<br/>
メンバー関数が検索される C 文字列。

*count*<br/>
メンバー関数が検索される C 文字列で、最初の文字から数えて、文字数。

*str*<br/>
メンバー関数が検索対象の string_view します。

### <a name="return-value"></a>戻り値

正常終了したときに部分文字列の最初の文字のインデックスそれ以外の場合`npos`します。

## <a name="size"></a>  basic_string_view::size

String_view 要素の数を返します。

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>戻り値

String_view の長さ。

### <a name="remarks"></a>Remarks

String_view はで、その長さをたとえば変更できます`remove_prefix`と`remove_suffix`します。 これには、基になる文字列データは変更しません、ため、string_view のサイズは必ずしも基になるデータのサイズ。

## <a name="substr"></a>  basic_string_view::substr

指定した位置から (最大で) 指定された文字数を表す string_view を返します。

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
元のコピーが行われる既定値は 0 の位置にある要素を検索するインデックス。

*count*<br/>
含まれている場合、部分文字列に含まれる文字数。

### <a name="return-value"></a>戻り値

要素のサブ指定のシーケンスを表す string_view オブジェクトを指定します。

## <a name="swap"></a>  basic_string_view::swap

2 つ string_views、つまり基になる文字列データでは、サイズの値にポインターを交換します。

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>パラメーター

*sv*<br/>
ポインタおよびサイズ値を持つが変換先の string_view のものと交換されるソース string_view します。

## <a name="see-also"></a>関連項目

[\<string_view>](../standard-library/string-view.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
