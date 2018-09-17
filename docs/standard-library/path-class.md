---
title: path クラス | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::path
dev_langs:
- C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd8fa524d0c41d437575a61ff4e4456fd9933404
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725310"
---
# <a name="path-class"></a>path クラス

**パス**クラス型のオブジェクトを格納する`string_type`という`myname`パス名として使用するための適切な説明の目的でここをクリックします。 `string_type` シノニムです`basic_string<value_type>`ここで、`value_type`のシノニムです**char** Windows 下または**wchar_t** Posix の下。

詳細およびコード例については、[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md) に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class path;
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[path](#path)|`path` を構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[const_iterator](#const_iterator)|`iterator` と同義。|
|[Iterator](#iterator)|指定する双方向定数反復子、`path`のコンポーネント`myname`します。|
|[string_type](#string_type)|この型は `basic_string<value_type>` の同意語です。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[append](#append)|指定したシーケンスに追加します`mypath`変換、および、必要に応じて preferred_separator の挿入します。|
|[assign](#assign)|置換`mypath`指定したシーケンスで必要に応じてを変換します。|
|[begin](#begin)|返します、`path::iterator`存在する場合、パス名の最初のパス要素を指定します。|
|[c_str](#c_str)|最初の文字へのポインターを返します`mypath`します。|
|[clear](#clear)|実行`mypath.clear()`します。|
|[compare](#compare)|比較する値を返します。|
|[concat](#compare)|指定したシーケンスに追加します`mypath`、変換 (ただし、区切り記号を挿入しない) 必要に応じて。|
|[empty](#empty)|`mypath.empty()` を返します。|
|[end](#end)|型のシーケンス末尾の反復子を返します`iterator`します。|
|[extension](#extension)|サフィックスを返します`filename()`します。|
|[ファイル名](#filename)|myname のルート ディレクトリ コンポーネント (具体的には、`empty() path() : *--end()`) を返します。 このコンポーネントは、空になることもあります。|
|[generic_string](#generic_string)|すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。|
|[generic_u16string](#generic_u16string)|すべての円記号がスラッシュに変換された `u16string()` を返します (Windows の場合)。|
|[generic_u32string](#generic_u32string)|すべての円記号がスラッシュに変換された `u32string()` を返します (Windows の場合)。|
|[generic_u8string](#generic_u8string)|すべての円記号がスラッシュに変換された `u8string()` を返します (Windows の場合)。|
|[generic_wstring](#generic_wstring)|すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。|
|[has_extension](#has_extension)|`!extension().empty()` を返します。|
|[has_filename](#has_filename)|`!filename().empty()` を返します。|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()` を返します。|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()` を返します。|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()` を返します。|
|[has_root_name](#has_root_name)|`!root_name().empty()` を返します。|
|[has_root_path](#has_root_path)|`!root_path().empty()` を返します。|
|[has_stem](#has_stem)|`!stem().empty()` を返します。|
|[is_absolute](#is_absolute)|Windows では、関数を返します`has_root_name() && has_root_directory()`します。 Posix 場合、関数を返します`has_root_directory()`します。|
|[is_relative](#is_relative)|`!is_absolute()` を返します。|
|[make_preferred](#make_preferred)|必要に応じて preferred_separator に各区切り記号に変換します。|
|[native](#native)|`myname` を返します。|
|[parent_path](#parent_path)|親のパス コンポーネントを返します`myname`します。|
|[preferred_separator](#preferred_separator)|この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。 |
|[relative_path](#relative_path)|相対パス コンポーネントを返します`myname`します。 |
|[remove_filename](#remove_filename)|ファイル名を削除します。|
|[replace_extension](#replace_extension)|拡張機能を置き換える`myname`します。 |
|[replace_filename](#replace_filename)|RReplaces ファイル名。|
|[ただし、物理的な](#root_directory)|ルート ディレクトリ コンポーネントを返します`myname`します。 |
|[root_name](#root_name)|ルート名の部分を返します`myname`します。 |
|[root_path](#root_path)|ルート パス コンポーネントを返します`myname`します。|
|[理工系](#stem)|返します、`stem`のコンポーネントである`myname`します。|
|[string](#string)|格納されているシーケンスに変換します`mypath`します。|
|[swap](#swap)|実行`swap(mypath, right.mypath)`します。|
|[u16string](#u16string)|格納されているシーケンスに変換します`mypath`を utf-16 型のオブジェクトに格納されていることを返す`u16string`します。|
|[u32string](#u32string)|格納されているシーケンスに変換します`mypath`utf-32 を型のオブジェクトに格納されていることを返す`u32string`します。|
|[u8string](#u8string)|格納されているシーケンスに変換します`mypath`を utf-8 型のオブジェクトに格納されていることを返す`u8string`します。|
|[value_type](#value_type)|この型は、ホスト オペレーティング システムに適したパス要素を表します。|
|[wstring](#wstring)|格納されているシーケンスに変換します`mypath`をホスト システムに適したエンコーディングを`wchar_t`シーケンスと型のオブジェクトに格納されていることを返します。`wstring`します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_as)|パスの要素を別のパスのコピーで置き換えます。|
|[operator+=](#op_add)|さまざまな`concat`式。|
|[operator/=](#op_divide)|さまざまな`append`式。|
|[operator string_type](#op_string)|`myname` を返します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="append"></a> path::append

指定したシーケンスに追加します`mypath`変換、および挿入を`preferred_separator`に応じて。

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*source*<br/>
指定されたシーケンス。

*first*<br/>
指定したシーケンスを開始します。

*last*<br/>
指定されたシーケンスの最後。

## <a name="assign"></a> path::assign

置換`mypath`指定したシーケンスで必要に応じてを変換します。

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*source*<br/>
指定されたシーケンス。

*first*<br/>
指定したシーケンスを開始します。

*last*<br/>
指定されたシーケンスの最後。

## <a name="begin"></a> path::begin

返します、`path::iterator`存在する場合、パス名の最初のパス要素を指定します。

```cpp
iterator begin() const;
```

## <a name="c_str"></a> path::c_str

最初の文字へのポインターを返します`mypath`します。

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a> path::clear

実行`mypath.clear()`します。

```cpp
void clear() noexcept;
```

## <a name="compare"></a> path::compare

最初の関数は `mypath.compare(pval.native())` を返します。 2 番目の関数は `mypath.compare(str)` を返します。 3 番目の関数を返します`mypath.compare(ptr)`します。

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
比較するパス。

*str*<br/>
比較する文字列。

*ptr*<br/>
比較するポインター。

## <a name="concat"></a> path::concat

指定したシーケンスに追加します`mypath`、変換 (ただし、区切り記号を挿入しない) 必要に応じて。

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*source*<br/>
指定されたシーケンス。

*first*<br/>
指定したシーケンスを開始します。

*last*<br/>
指定されたシーケンスの最後。

## <a name="const_iterator"></a> path::const_iterator

`iterator` と同義。

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a> path::empty

`mypath.empty()` を返します。

```cpp
bool empty() const noexcept;
```

## <a name="end"></a> path::end

型のシーケンス末尾の反復子を返します`iterator`します。

```cpp
iterator end() const;
```

## <a name="extension"></a> path::extension

サフィックスを返します`filename()`します。

```cpp
path extension() const;
```

### <a name="remarks"></a>Remarks

サフィックスを返します`filename() X`ように。

場合`X == path(".") || X == path("..")`場合`X`のドットが含まれていない、サフィックスは空です。

それ以外の場合、サフィックスは一番右にあるドットから始まります (このドットも含む)。

## <a name="filename"></a> path::filename

myname のルート ディレクトリ コンポーネント (具体的には、`empty() path() : *--end()`) を返します。 このコンポーネントは、空になることもあります。

```cpp
path filename() const;
```

## <a name="generic_string"></a> path::generic_string

すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a> path::generic_u16string

すべての円記号がスラッシュに変換された `u16string()` を返します (Windows の場合)。

```cpp
u16string generic_u16string() const;
```

## <a name="generic_u32string"></a> path::generic_u32string

すべての円記号がスラッシュに変換された `u32string()` を返します (Windows の場合)。

```cpp
u32string generic_u32string() const;
```

## <a name="generic_u8string"></a> path::generic_u8string

すべての円記号がスラッシュに変換された `u8string()` を返します (Windows の場合)。

```cpp
string generic_u8string() const;
```

## <a name="generic_wstring"></a> path::generic_wstring

すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a> path::has_extension

`!extension().empty()` を返します。

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a> path::has_filename

`!filename().empty()` を返します。

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a> path::has_parent_path

`!parent_path().empty()` を返します。

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a> path::has_relative_path

`!relative_path().empty()` を返します。

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a> path::has_root_directory

`!root_directory().empty()` を返します。

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a> path::has_root_name

`!root_name().empty()` を返します。

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a> path::has_root_path

`!root_path().empty()` を返します。

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a> path::has_stem

`!stem().empty()` を返します。

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a> path::is_absolute

Windows では、関数を返します`has_root_name() && has_root_directory()`します。 Posix 場合、関数を返します`has_root_directory()`します。

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a> path::is_relative

`!is_absolute()` を返します。

```cpp
bool is_relative() const;
```

## <a name="iterator"></a> path::iterator

パス コンポーネントを指定する双方向定数反復子`myname`します。

```cpp
class iterator
   {
   // bidirectional iterator for path
   typedef bidirectional_iterator_tag iterator_category;
   typedef path_type value_type;
   typedef ptrdiff_t difference_type;
   typedef const value_type *pointer;
   typedef const value_type& reference;
   // ...
   };
```

### <a name="remarks"></a>Remarks

クラスの説明を指定する双方向定数反復子、`path`のコンポーネント`myname`シーケンス。

1. ルート名 (存在する場合)

1. ルート ディレクトリ (存在する場合)

1. 親の残りの directory 要素`path`存在するか、存在する場合、ファイル名で終わる場合、

`pval`型のオブジェクト`path`:

1. `path::iterator X = pval.begin()` 最初に指定`path`要素が存在する場合、pathname にします。

1. `X == pval.end()` 場合は true`X`コンポーネントのシーケンスの末尾の直後のポイント。

3. `*X` 現在の要素に一致する文字列を返します

1. `++X` は、シーケンス内に次のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. `--X` は、シーケンス内に前のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. 変更`myname`内の要素を指定するすべての反復子を無効に`myname`します。

## <a name="make_preferred"></a> path::make_preferred

各区切り記号を変換、`preferred_separator`に応じて。

```cpp
path& make_preferred();
```

## <a name="native"></a> path::native

`myname` を返します。

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a> path::operator =

パスの要素を別のパスのコピーで置き換えます。

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[パス](../standard-library/path-class.md)にコピーされる、`path`します。

*source*<br/>
ソースのパス。

### <a name="remarks"></a>Remarks

最初のメンバー演算子コピー`right.myname`に`myname`します。 2 番目のメンバー演算子は、移動`right.myname`に`myname`します。 3 番目のメンバー演算子の動作と同じ`*this = path(source)`します。

## <a name="op_add"></a> path::operator + =

さまざまな`concat`式。

```cpp
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);

template <class Source>
path& operator+=(const Source& source);

template <class Elem>
path& operator+=(Elem elem);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
追加されたパス。

*str*<br/>
追加された文字列。

*ptr*<br/>
追加のポインター。

*Elem*<br/>
追加された`value_type`または`Elem`します。

*source*<br/>
追加のソース。

### <a name="remarks"></a>Remarks

このメンバー関数には、次の対応する式と同じ効果があります。

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a> path::operator/=

さまざまな`append`式。

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
追加されたパス。

*source*<br/>
追加のソース。

### <a name="remarks"></a>Remarks

このメンバー関数には、次の対応する式と同じ効果があります。

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a> path::operator string_type

`myname` を返します。

```cpp
operator string_type() const;
```

## <a name="parent_path"></a> path::parent_path

親のパス コンポーネントを返します`myname`します。

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Remarks

親のパス コンポーネントを返します`myname`、具体的には、プレフィックス`myname`を削除した後`filename().native()`と、直前のディレクトリの区切り記号。 (同様に場合、 `begin() != end()`、範囲内のすべての要素の結合は`[begin(), --end())`連続して適用することで`operator/=`)。このコンポーネントは、空になることもあります。

## <a name="path"></a> path::path

構築、`path`さまざまな方法でします。

```cpp
path();

path(const path& right);
path(path&& right) noexcept;

template <class Source>
path(const Source& source);

template <class Source>
path(const Source& source, const locale& loc);

template <class InIt>
path(InIt first, InIt last);

template <class InIt>
path(InIt first, InIt last, const locale& loc);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
構築されたパスがコピーのパス。

*source*<br/>
構築されたパスがコピーのソース。

*Loc*<br/>
指定されたロケール。

*first*<br/>
コピーされる最初の要素の位置。

*last*<br/>
コピーする最後の要素の位置。

### <a name="remarks"></a>Remarks

すべてを作成するコンス トラクター`myname`さまざまな方法で。

`path()`は`myname()`します。

`path(const path& right`) は`myname(right.myname)`します。

`path(path&& right)`は`myname(right.myname)`します。

`template<class Source> path(const Source& source)`は`myname(source)`します。

`template<class Source> path(const Source& source, const locale& loc)`は`myname(source)`、必要な codecvt ファセットからのいずれかを取得する`loc`します。

`template<class InIt> path(InIt first, InIt last)`は`myname(first, last)`します。

`template<class InIt> path(InIt first, InIt last, const locale& loc)`は`myname(first, last)`、必要な codecvt ファセットからのいずれかを取得する`loc`します。

## <a name="preferred_separator"></a> path::preferred_separator

この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>Remarks

Windows では、ほとんどのコンテキストで、L'/' の代用が許容されます。

## <a name="relative_path"></a> path::relative_path

相対パス コンポーネントを返します`myname`します。

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Remarks

相対パス コンポーネントを返します`myname`、具体的には、サフィックスの`myname`を削除した後`root_path().native()`と任意の直後の冗長なディレクトリ区切り記号。 このコンポーネントは、空になることもあります。

## <a name="remove_filename"></a> path::remove_filename

ファイル名を削除します。

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a> path::replace_extension

拡張機能を置き換える`myname`します。

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>パラメーター

*最後に、newext*<br/>
新しい拡張機能。

### <a name="remarks"></a>Remarks

最初に、サフィックスを削除`extension().native()`から`myname`します。 場合、 `!newext.empty() && newext[0] != dot` (場所`dot`は`*path(".").c_str()`)、し`dot`に追加される`myname`します。 *Newext*に追加される`myname`します。

## <a name="replace_filename"></a> path::replace_filename

ファイル名に置き換えます。

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
ファイル名のパス。

### <a name="remarks"></a>Remarks

このメンバー関数は、次のコードを実行します。

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a> path::root_directory

ルート ディレクトリ コンポーネントを返します`myname`します。

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Remarks

このコンポーネントは、空になることもあります。

## <a name="root_name"></a> path::root_name

ルート名の部分を返します`myname`します。

```cpp
path root_name() const;
```

### <a name="remarks"></a>Remarks

このコンポーネントは、空になることもあります。

## <a name="root_path"></a> path::root_path

ルート パス コンポーネントを返します`myname`します。

```cpp
path root_path() const;
```

### <a name="remarks"></a>Remarks

ルート パス コンポーネントを返します`myname`、特に`root_name()`  / `root_directory`します。 このコンポーネントは、空になることもあります。

## <a name="stem"></a> path::stem

返します、`stem`のコンポーネントである`myname`します。

```cpp
path stem() const;
```

### <a name="remarks"></a>Remarks

返します、`stem`のコンポーネントである`myname`、特に`filename().native()`の末尾に、`extension().native()`削除します。 このコンポーネントは、空になることもあります。

## <a name="string"></a> path::string

格納されているシーケンスに変換します`mypath`します。

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Remarks

最初の (テンプレート) メンバー関数が格納されているシーケンスに変換します`mypath`と同じ方法。

1. `string<char, Traits, Alloc>()` の `string()`

1. `string<wchar_t, Traits, Alloc>()` の `wstring()`

1. `string<char16_t, Traits, Alloc>()` の `u16string()`

1. `string<char32_t, Traits, Alloc>()` の `u32string()`

2 番目のメンバー関数が格納されているシーケンスに変換します`mypath`をホスト システムに適したエンコーディングを**char**シーケンスと型のオブジェクトに格納されていることを返します。`string`します。

## <a name="string_type"></a> path::string_type

この型は `basic_string<value_type>` の同意語です。

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a> path::swap

実行`swap(mypath, right.mypath)`します。

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a> path::u16string

格納されているシーケンスに変換します`mypath`を utf-16 型のオブジェクトに格納されていることを返す`u16string`します。

```cpp
u16string u16string() const;
```

## <a name="u32string"></a> path::u32string

格納されているシーケンスに変換します`mypath`utf-32 を型のオブジェクトに格納されていることを返す`u32string`します。

```cpp
u32string u32string() const;
```

## <a name="u8string"></a> path::u8string

格納されているシーケンスに変換します`mypath`を utf-8 型のオブジェクトに格納されていることを返す`u8string`します。

```cpp
string u8string() const;
```

## <a name="value_type"></a> path::value_type

型について説明します、`path`をホスト オペレーティング システムの要素。

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a> path::wstring

格納されているシーケンスに変換します`mypath`をホスト システムに適したエンコーディングを**wchar_t**シーケンスと型のオブジェクトに格納されていることを返します。`wstring`します。

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
