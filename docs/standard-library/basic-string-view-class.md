---
title: basic_string_viewクラス
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
ms.openlocfilehash: ac65dca931f821c717e9c081c8d3479fd0b3bb0e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364894"
---
# <a name="basic_string_view-class"></a>basic_string_viewクラス

C++ `basic_string_view<charT>` 17 では、クラス テンプレートが追加され、関数がさまざまな無関係な文字列型を受け入れるための安全で効率的な方法として機能します。 このクラスは、連続する文字データ・シーケンスへの非所有ポインター、およびシーケンス内の文字数を指定する長さを保持します。 シーケンスが NULL で終わるかどうかについては、想定されません。

標準ライブラリは、要素の型に基づいていくつかの特殊化を定義します。

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

この文書では、"string_view" という用語は、一般にこれらのタイプ定義のいずれかを指します。

string_viewは、文字列データの読み取りに必要な最低限の共通インターフェイスを記述します。 基になるデータへの const アクセスを提供します。コピーは行いません (関数を`copy`除く)。 データには、任意の位置に NULL 値 ('\0') が含まれている場合と含まれていない場合があります。 string_viewは、オブジェクトの有効期間を制御しません。 基になる文字列データが有効であることを確認するのは、呼び出し元の責任です。

型string_viewのパラメーターを受け取る関数は、関数をテンプレートにしたり、関数を文字列型の特定のサブセットに制限したりすることなく、文字列のような型で動作させることができます。 唯一の要件は、文字列型からstring_viewへの暗黙的な変換が存在することです。 すべての標準文字列型は、同じ要素型を含むstring_viewに暗黙的に変換できます。 つまり、 は`std::string`変換できますが、 には`string_view`変換できません。 `wstring_view`

次の例は、type 型`f``wstring_view`のパラメーターを受け取る非テンプレート関数を示しています。 型`std::wstring`、、`wchar_t*`および`winrt::hstring`の引数を指定して呼び出すことができます。

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

*Chartype*\
string_viewに格納されている文字の型。 C++ 標準ライブラリには、このテンプレートの特殊化に関する次の typedef が用意されています。

- [char](../standard-library/string-view-typedefs.md#string_view)型の要素**char**のstring_view
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), **wchar_t**用
- [char16_t](../standard-library/string-view-typedefs.md#u16string_view)の**char16_t**u16string_view
- **char32_t**の[u32string_view。](../standard-library/string-view-typedefs.md#u32string_view)

*特徴*\
デフォルトは[、char_traits](char-traits-struct.md)<*CharType*>です。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_string_view](#basic_string_view)|空のstring_viewを構築するか、その他の文字列オブジェクトのデータの全部または一部、または C スタイルの文字配列を指す。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|**const_iterator**|**const**要素を読み取ることができるランダム アクセス反復子。|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**反復 子**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**ポインター (pointer)**|`using pointer = value_type*;`|
|**参照**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**Size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**Value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>メンバー演算子

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|string_viewまたは変換可能な文字列オブジェクトを別のstring_viewに割り当てます。|
|[演算子\[\]](#op_at)|指定したインデックス位置にある要素を返します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[で](#at)|指定した位置にある要素に対するconst_referenceを返します。|
|[戻る](#back)|最後の要素にconst_referenceを返します。|
|[開始](#begin)|最初の要素をアドレス指定する const 反復子を返します。 (string_viewsは不変です。|
|[cbegin](#cbegin)|[開始](#begin)と同じ。|
|[クエンド](#cend)|最後の要素の 1 つ後を指す const 反復子を返します。|
|[コピー](#copy)|ソースstring_view内のインデックス位置から、指定された文字数をコピーします。 (お勧めしません。 代わりに_Copy_sを使用してください)。|
|[_Copy_s](#_copy_s)|CRT コピー機能を保護します。|
|[比較](#compare)|string_viewと指定されたstring_viewを比較して、それらが等しいかどうか、または一方が他方より辞書的に少ないかどうかを判断します。|
|[crbegin](#crbegin)|[rbegin](#rbegin)と同じです。|
|[crend](#crend)|[レンド](#rend)と同じです。|
|[データ](#data)|文字シーケンスへの未所有のポインターを返します。|
|[empty](#empty)|string_viewに文字が含まれているかどうかをテストします。|
|[end](#end)|[クエンド](#cend)と同じ.|
|[find](#find)|指定された文字のシーケンスに一致する部分文字列の最初の出現を前方方向で検索します。|
|[find_first_not_of](#find_first_not_of)|指定したstring_viewまたはコンバーティブル文字列オブジェクトの要素ではない最初の文字を検索します。|
|[find_first_of](#find_first_of)|指定したstring_viewまたは変換可能な文字列オブジェクトの要素に一致する最初の文字を検索します。|
|[find_last_not_of](#find_last_not_of)|指定したstring_viewまたは変換可能な文字列オブジェクトの要素以外の最後の文字を検索します。|
|[find_last_of](#find_last_of)|指定したstring_viewまたは変換可能な文字列オブジェクトの要素である最後の文字を検索します。|
|[フロント](#front)|最初の要素にconst_referenceを返します。|
|[length](#length)|現在の要素数を返します。|
|[max_size](#max_size)|string_viewに含めることができる最大文字数を返します。|
|[rbegin](#rbegin)|逆string_viewの最初の要素をアドレス指定する const 反復子を返します。|
|[remove_prefix](#remove_prefix)|指定した数の要素でポインタを前方に移動します。|
|[remove_suffix](#remove_suffix)|ビューのサイズを、指定した数だけ背面から開始します。|
|[rend](#rend)|逆string_viewの最後の要素を 1 つ超える位置を指す const 反復子を返します。|
|[rfind](#rfind)|指定した文字のシーケンスに一致する部分文字列が最初に出現するかどうかを、string_viewを逆方向に検索します。|
|[サイズ](#size)|現在の要素数を返します。|
|[substr](#substr)|指定したインデックス位置から、指定した長さの部分文字列を返します。|
|[スワップ](#swap)|2つのstring_viewsの内容を交換します。|

## <a name="remarks"></a>解説

関数が [max_size](#max_size) の要素よりも長いシーケンスを生成するように指示された場合、関数は [length_error](../standard-library/length-error-class.md) 型のオブジェクトをスローして長さエラーを報告します。

## <a name="requirements"></a>必要条件

[std:c++17](../build/reference/std-specify-language-standard-version.md)以降

**ヘッダー:** \<string_view>

**名前空間:** std

## <a name="basic_string_viewat"></a><a name="at"></a>basic_string_view::at

指定した 0 から始まるインデックス位置にある文字に対するconst_referenceを返します。

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*\
参照される要素のインデックス。

### <a name="return-value"></a>戻り値

パラメーター索引で指定された位置にある文字に対するconst_reference。

### <a name="remarks"></a>解説

最初の要素はインデックスが 0 で、次の要素は正の整数で連続してインデックス付けされるため、長さ*n*の*n*string_viewは n 番目の要素が*n から*1 の数でインデックス付けされます。 **は**[、演算子\[](#op_at)とは異なり、無効なインデックスの例外をスローします。

一般に、string_viewなどの**at**`std::vector`シーケンスでは、使用しないでください。 シーケンスに渡される無効なインデックスは、開発中に検出および修正する必要がある論理エラーです。 プログラムがインデックスが有効であることを確実にしない場合は、at() を呼び出すのではなく、テストし、不注意なプログラミングから防御するために例外に頼る必要があります。

詳細については[、basic_string_view::演算子\[](#op_at)を参照してください。

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

## <a name="basic_string_viewback"></a><a name="back"></a>basic_string_view::戻る

最後の要素にconst_referenceを返します。

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>戻り値

string_viewの最後の要素にconst_reference。

### <a name="remarks"></a>解説

string_viewが空の場合に例外をスローします。

string_viewを変更した後 、たとえば を呼び出`remove_suffix`すと、この関数によって返される要素は、基になるデータの最後の要素ではなくなります。

### <a name="example"></a>例

C 文字列リテラルで構築されたstring_viewには終了 NULL が含まれていないため、次の例では`back`'p' を返し、'\0' を返しません。

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

埋め込みヌルは、他の文字として扱われます。

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a>basic_string_view::basic_string_view

string_viewを構築します。

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>パラメーター

*Str*\
文字値へのポインター。

*Len*\
ビューに含める文字数。

## <a name="remarks"></a>解説

charT* パラメーターを持つコンストラクターは、入力が null で終わるものと想定していますが、終端の null はstring_viewに含まれません。

リテラルを使用してstring_viewを構築することもできます。 [演算子"sv を](string-view-operators.md#op_sv)参照してください。

## <a name="basic_string_viewbegin"></a><a name="begin"></a>basic_string_view::開始

[cbegin](#cbegin)と同じです。

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>戻り値

最初の要素をアドレス指定するconst_iteratorを返します。

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a>basic_string_view::cbegin

範囲内の最初の要素を指定するconst_iteratorを返します。

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

範囲の最初の要素、または空の範囲の終わりを越えた位置を指す**const**ランダム アクセス反復子 (空の範囲の場合)。 `cbegin() == cend()`

## <a name="basic_string_viewcend"></a><a name="cend"></a>basic_string_view::cend

範囲内の最後の要素を越える位置を指定するconst_iteratorを返します。

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>戻り値

範囲の終わりを越えて指す**const**ランダム アクセス反復器。

### <a name="remarks"></a>解説

`cend` によって返された値は逆参照しないでください。

## <a name="basic_string_viewcompare"></a><a name="compare"></a>basic_string_view::比較

指定したstring_view (または変換可能な文字列型) と大文字と小文字を区別した比較を実行して、2 つのオブジェクトが等しいかどうか、または一方が他方より辞書的に少ないかどうかを判断します。 [ \<string_view>演算子](string-view-operators.md)は、このメンバー関数を使用して比較を実行します。

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>パラメーター

*ストルヴ*\
このstring_viewと比較されるstring_view。

*Pos*\
比較が開始されるこのstring_viewのインデックス。

*Num*\
このstring_viewから比較される最大文字数。

*num2*\
比較する*strv*からの最大文字数。

*オフセット*\
比較が開始される*strv*のインデックス。

*Ptr*\
このstring_viewと比較する C 文字列。

### <a name="return-value"></a>戻り値

このstring_viewが*strv*または*ptr*より小さい場合は負の値。2 つの文字シーケンスが等しい場合は 0。このstring_viewが*strv*または*ptr*より大きい場合は正の値を指定します。

### <a name="remarks"></a>解説

メンバー`compare`関数は、各文字シーケンスの全部または一部の大文字と小文字を区別した比較を実行します。

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

## <a name="basic_string_viewcopy"></a><a name="copy"></a>basic_string_view::コピー

ソースstring_view内のインデックス位置から、指定された文字数をコピーします。 代わりに[、basic_string_view::_Copy_s](#_copy_s)を使用することをお勧めします。

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*Ptr*\
要素のコピー先のターゲット文字配列。

*カウント*\
ソース string_viewからコピーされる文字の数。

*オフセット*\
コピーの作成元string_viewソース内の開始位置。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。

### <a name="remarks"></a>解説

null 文字はコピーの末尾には追加されません。

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a>basic_string_view::_Copy_s

コピーの代わりに使用するセキュア CRT[コピー](#copy)機能 .

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>パラメーター

*Dest*\
要素のコピー先のターゲット文字配列。

*dest_size*\
*最も大きなサイズ*.

*_Count*ソース文字列からコピーされる文字の数です。

*_Off*\
ソース文字列内のコピーの作成開始位置。

### <a name="return-value"></a>戻り値

実際にコピーされた文字数。

### <a name="remarks"></a>解説

null 文字はコピーの末尾には追加されません。

詳細については、「 [c-runtime-library/セキュリティ機能 -in-the-crt](../c-runtime-library/security-features-in-the-crt.md)」を参照してください。

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a>basic_string_view::クリbegin

逆string_viewの最初の要素をアドレス指定するconst_reverse_iteratorを返します。

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

逆string_viewの最初の要素をアドレス指定するconst_reverse_iterator。

## <a name="basic_string_viewcrend"></a><a name="crend"></a>basic_string_view::クレンド

[レンド](#rend)と同じです。

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>戻り値

逆string_viewの終わりより後のアドレスを指定するconst_reverse_iteratorを返します。

## <a name="basic_string_viewdata"></a><a name="data"></a>basic_string_view::dタータ

string_viewの構築に使用されたオブジェクトの const 文字シーケンスを指す、未所有の未所有のポインターを返します。

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>戻り値

文字シーケンスの最初の要素へのポインターです。

### <a name="remarks"></a>解説

ポインタは文字を変更できません。

string_view文字のシーケンスは、必ずしもヌル終了ではありません。 null 文字が`data`追加されないため、戻り値の型は有効な C 文字列ではありません。 null 文字 '\0' は、string_view型のオブジェクトでは特別な意味を持たないため、他の文字と同じようにstring_viewオブジェクトの一部である可能性があります。

## <a name="basic_string_viewempty"></a><a name="empty"></a>basic_string_view::空

string_viewに文字が含まれているかどうかをテストします。

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>戻り値

string_view オブジェクトに文字が含まれなかった場合は**true、** 少なくとも 1 文字の場合は**false。**

### <a name="remarks"></a>解説

メンバー関数は[、サイズ](#size)() == 0 と同等です。

## <a name="basic_string_viewend"></a><a name="end"></a>basic_string_view::終了

最後の要素の 1 つ後を指すランダム アクセス const_iteratorを返します。

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>戻り値

最後の要素の 1 つ後を指すランダム アクセス const_iteratorを返します。

### <a name="remarks"></a>解説

`end`は、const_iteratorがstring_viewの終わりに達したかどうかをテストするために使用されます。 `end` によって返された値は逆参照しないでください。

## <a name="basic_string_viewfind"></a><a name="find"></a>basic_string_view::検索

指定された文字シーケンスに一致する文字または部分文字列が最初に出現するかどうかを前方方向でstring_viewを検索します。

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*Str*\
メンバー関数が検索対象のstring_view。

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索を開始するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
最初の文字から順にカウントされる*ptr*内の文字数。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string_view::find_first_not_of

指定したstring_viewまたは変換可能な文字列オブジェクトの要素ではない最初の文字を検索します。

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*Str*\
メンバー関数が検索対象のstring_view。

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索を開始するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
メンバー関数が検索対象となる C 文字列の最初の文字から順にカウントされる文字数。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a>basic_string_view::find_first_of

指定したstring_viewの要素に一致する最初の文字を検索します。

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>パラメーター

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索を開始するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
メンバー関数が検索対象となる C 文字列の最初の文字から順にカウントされる文字数。

*Str*\
メンバー関数が検索対象のstring_view。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `npos`。

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string_view::find_last_not_of

指定したstring_viewの要素以外の最後の文字を検索します。

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*Str*\
メンバー関数が検索対象のstring_view。

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索が終了するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
最初の文字から順にカウントされる文字数を*ptr*で指定します。

### <a name="return-value"></a>戻り値

成功した場合、検索する部分文字列の最初の文字のインデックス、それ以外の場合 `string_view::npos`。

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a>basic_string_view::find_last_of

指定したstring_viewの要素と一致する最後の文字を検索します。

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*Str*\
メンバー関数が検索対象のstring_view。

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索が終了するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
メンバー関数が検索対象となる C 文字列の最初の文字から順にカウントされる文字数。

### <a name="return-value"></a>戻り値

成功した場合は検索する部分文字列の最後の文字のインデックス、それ以外の場合は `npos`。

## <a name="basic_string_viewfront"></a><a name="front"></a>basic_string_view::フロント

最初の要素にconst_referenceを返します。

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>戻り値

最初の要素へのconst_reference。

### <a name="remarks"></a>解説

string_viewが空の場合に例外をスローします。

## <a name="basic_string_viewlength"></a><a name="length"></a>basic_string_view::長さ

現在の要素数を返します。

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>解説

このメンバー関数は [size](#size) と同じです。

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a>basic_string_view::max_size

string_viewに含めることができる最大文字数を返します。

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>戻り値

string_viewに含めることができる最大文字数。

### <a name="remarks"></a>解説

length_error[型の](../standard-library/length-error-class.md)例外は、操作が長さが より`max_size()`大きいstring_viewを生成したときにスローされます。

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a>basic_string_view::演算子=

string_viewまたは変換可能な文字列オブジェクトを別のstring_viewに割り当てます。

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>例

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a>basic_string_view::演算子[]

指定したインデックスを持つ文字にconst_referenceを提供します。

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*\
参照される要素のインデックス。

### <a name="return-value"></a>戻り値

パラメーター索引で指定された位置にある文字に対するconst_reference。

### <a name="remarks"></a>解説

最初の要素はインデックスが 0 で、次の要素は正の整数で連続してインデックス付けされるため、長さ*n*のstring_viewは*n*番目の要素が*n*から 1 の数でインデックス付けされます。

`operator[]`は、string_viewの要素に対する読み取りアクセスを[提供する場合](#at)のメンバー関数よりも高速です。

`operator[]`引数として渡されたインデックスが有効かどうかはチェックしません。 無効なインデックスが渡`operator[]`された場合、未定義の動作が発生します。

基になる文字列データが所有オブジェクトによって変更または削除された場合、返される参照が無効になる可能性があります。

[ \_ITERATOR\_\_DEBUG LEVEL](../standard-library/iterator-debug-level.md)を 1 または 2 に設定してコンパイルする場合、string_viewの範囲外の要素にアクセスしようとすると、ランタイム エラーが発生します。 詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a>basic_string_view::始まり

逆string_viewの最初の要素に対する const 反復子を返します。

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>戻り値

逆string_viewの最初の要素へのランダム アクセス反復子を返し、対応する反転されていないstring_viewの最後の要素を指定します。

### <a name="remarks"></a>解説

`rbegin`は[、string_view](#begin)で begin を使用するのと同じように、逆string_viewと共に使用されます。 `rbegin`は、反復を逆方向に初期化するために使用できます。

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a>basic_string_view::remove_prefix

指定した数の要素でポインタを前方に移動します。

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>解説

基になるデータは変更されません。 string_viewポインタを n 要素ずつ前方に移動し`size`、プライベート データ メンバを size - n に設定します。

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a>basic_string_view::remove_suffix

ビューのサイズを、指定した数だけ背面から開始します。

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>解説

基になるデータとそれに対するポインタは変更されません。 プライベート`size`データ メンバーのサイズを n に設定します。

## <a name="basic_string_viewrend"></a><a name="rend"></a>basic_string_view::レンド

逆string_viewの最後の要素を 1 つ超える位置を指す const 反復子を返します。

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>戻り値

逆string_viewの最後の要素を 1 つ超えて指す const 逆順ランダム アクセス反復子。

### <a name="remarks"></a>解説

`rend`は[、string_view](#end)で end を使用するのと同じように、逆string_viewと共に使用されます。 `rend`逆反復器がstring_viewの終わりに達したかどうかをテストするために使用できます。 `rend` によって返された値は逆参照しないでください。

## <a name="basic_string_viewrfind"></a><a name="rfind"></a>basic_string_view::rfind

指定した文字シーケンスに一致する部分文字列を逆方向にstring_view検索します。

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>パラメーター

*chVal*\
メンバー関数が検索される文字値。

*オフセット*\
検索を開始するインデックス。

*Ptr*\
メンバー関数が検索対象となる C 文字列。

*カウント*\
メンバー関数が検索対象となる C 文字列の最初の文字から順にカウントされる文字数。

*Str*\
メンバー関数が検索対象のstring_view。

### <a name="return-value"></a>戻り値

成功した場合は、部分文字列の最初の文字のインデックス。それ`npos`以外の場合は、

## <a name="basic_string_viewsize"></a><a name="size"></a>basic_string_view::サイズ

string_view内の要素の数を返します。

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>戻り値

string_viewの長さ。

### <a name="remarks"></a>解説

string_viewは、`remove_prefix`や`remove_suffix`などによって長さを変更できます。 これにより、基になる文字列データが変更されるわけではないため、string_viewのサイズは、必ずしも基になるデータのサイズとは限りません。

## <a name="basic_string_viewsubstr"></a><a name="substr"></a>basic_string_view::サブストル

指定した位置から指定した文字数を (多く) 表すstring_viewを返します。

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>パラメーター

*オフセット*\
要素をコピー元の位置に配置するインデックスで、既定値は 0 です。

*カウント*\
サブストリングに含める文字数 (存在する場合)。

### <a name="return-value"></a>戻り値

指定した要素のサブシーケンスを表すstring_view オブジェクト。

## <a name="basic_string_viewswap"></a><a name="swap"></a>basic_string_view::スワップ

2 つのstring_views、つまり、基になる文字列データへのポインターとサイズの値を交換します。

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>パラメーター

*Sv*\
ポインターとサイズの値が変換先のstring_viewの値と交換されるソース string_view。

## <a name="see-also"></a>関連項目

[\<>string_view](../standard-library/string-view.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
