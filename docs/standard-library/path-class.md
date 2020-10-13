---
title: path クラス
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: fb56afbc1d29f1d321b394342382f89b06768720
ms.sourcegitcommit: b5854134553db1d99a5761bec131841c374a3098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "91958660"
---
# <a name="path-class"></a>path クラス

**Path**クラスは、型のオブジェクトを格納し `string_type` ます。これは、パス `myname` 名としての使用に適した、exposition の目的でここで呼び出されます。 `string_type` はのシノニムです `basic_string<value_type>` 。ここで、 `value_type` は Windows 上ののシノニムで、 **`wchar_t`** **`char`** POSIX ではです。

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
|[反](#iterator)|のコンポーネントを指定する双方向定数反復子 `path` `myname` 。|
|[string_type](#string_type)|この型は `basic_string<value_type>` の同意語です。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[append](#append)|必要に応じて、指定したシーケンスをに追加し `mypath` 、変換して、preferred_separator 挿入します。|
|[assign](#assign)|必要に応じ `mypath` て変換された、指定したシーケンスで置き換えます。|
|[初め](#begin)|パス `path::iterator` 名の最初のパス要素 (存在する場合) を示すを返します。|
|[c_str](#c_str)|の最初の文字へのポインターを返し `mypath` ます。|
|[オフ](#clear)|`mypath.clear()`を実行します。|
|[対照](#compare)|比較値を返します。|
|[concat](#compare)|必要に応じて、指定したシーケンスをに追加し `mypath` ます (区切り記号は挿入しません)。|
|[empty](#empty)|`mypath.empty()` を返します。|
|[end](#end)|型のシーケンスの末尾の反復子を返し `iterator` ます。|
|[extension](#extension)|のサフィックスを返し `filename()` ます。|
|[filename](#filename)|myname のルート ディレクトリ コンポーネント (具体的には、 `empty() ? path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。|
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
|[is_absolute](#is_absolute)|Windows の場合、関数はを返し `has_root_name() && has_root_directory()` ます。 POSIX の場合、関数はを返し `has_root_directory()` ます。|
|[is_relative](#is_relative)|`!is_absolute()` を返します。|
|[make_preferred](#make_preferred)|各区切り記号を必要に応じて preferred_separator に変換します。|
|[native](#native)|`myname` を返します。|
|[parent_path](#parent_path)|の親パスコンポーネントを返し `myname` ます。|
|[preferred_separator](#preferred_separator)|この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。 |
|[relative_path](#relative_path)|の相対パスコンポーネントを返し `myname` ます。 |
|[remove_filename](#remove_filename)|ファイル名を削除します。|
|[replace_extension](#replace_extension)|の拡張機能を置き換え `myname` ます。 |
|[replace_filename](#replace_filename)|ファイル名を置き換えます。|
|[root_directory](#root_directory)|のルートディレクトリコンポーネントを返し `myname` ます。 |
|[root_name](#root_name)|のルート名コンポーネントを返し `myname` ます。 |
|[root_path](#root_path)|のルートパスコンポーネントを返し `myname` ます。|
|[stem](#stem)|`stem`のコンポーネントを返し `myname` ます。|
|[string](#string)|に格納されているシーケンスを変換 `mypath` します。|
|[スワップ](#swap)|`swap(mypath, right.mypath)`を実行します。|
|[u16string](#u16string)|に格納されているシーケンスを `mypath` utf-16 に変換し、型のオブジェクトに格納して返し `u16string` ます。|
|[u32string](#u32string)|に格納されているシーケンスを `mypath` 32 utf-8 に変換し、型のオブジェクトに格納されているを返し `u32string` ます。|
|[u8string](#u8string)|に格納されているシーケンスを `mypath` utf-8 に変換し、型のオブジェクトに格納して返し `u8string` ます。|
|[value_type](#value_type)|この型は、ホスト オペレーティング システムに適したパス要素を表します。|
|[wstring](#wstring)|に格納されているシーケンスを、 `mypath` シーケンスのホストシステムによって優先されるエンコーディングに変換 **`wchar_t`** し、型のオブジェクトに格納して返し `wstring` ます。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator =](#op_as)|パスの要素を別のパスのコピーで置き換えます。|
|[演算子 + =](#op_add)|さまざまな `concat` 式。|
|[operator/=](#op_divide)|さまざまな `append` 式。|
|[string_type 演算子](#op_string)|`myname` を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<filesystem>

**名前空間:** std::experimental::filesystem

## <a name="pathappend"></a><a name="append"></a> path:: append

必要に応じて、指定したシーケンスをに追加し `mypath` 、変換して、挿入し `preferred_separator` ます。

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*電源*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの最後。

## <a name="pathassign"></a><a name="assign"></a> パス:: assign

必要に応じ `mypath` て変換された、指定したシーケンスで置き換えます。

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*電源*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの最後。

## <a name="pathbegin"></a><a name="begin"></a> path:: begin

パス `path::iterator` 名の最初のパス要素 (存在する場合) を示すを返します。

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a> パス:: c_str

の最初の文字へのポインターを返し `mypath` ます。

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a> パス:: clear

`mypath.clear()`を実行します。

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a> path:: compare

最初の関数は `mypath.compare(pval.native())` を返します。 2 番目の関数は `mypath.compare(str)` を返します。 3番目の関数はを返し `mypath.compare(ptr)` ます。

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>パラメーター

*pval*\
比較するパス。

*引数*\
比較する文字列。

*ポインター*\
比較するポインター。

## <a name="pathconcat"></a><a name="concat"></a> path:: concat

必要に応じて、指定したシーケンスをに追加し `mypath` ます (区切り記号は挿入しません)。

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*電源*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの最後。

## <a name="pathconst_iterator"></a><a name="const_iterator"></a> パス:: const_iterator

`iterator` と同義。

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a> path:: empty

`mypath.empty()` を返します。

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a> パス:: 終了

型のシーケンスの末尾の反復子を返し `iterator` ます。

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a> path:: extension

のサフィックスを返し `filename()` ます。

```cpp
path extension() const;
```

### <a name="remarks"></a>注釈

次のようなのサフィックスを返し `filename() X` ます。

に `X == path(".") || X == path("..")` ドットが `X` 含まれていない場合、サフィックスは空になります。

それ以外の場合、サフィックスは一番右にあるドットから始まります (このドットも含む)。

## <a name="pathfilename"></a><a name="filename"></a> パス:: ファイル名

myname のルート ディレクトリ コンポーネント (具体的には、 `empty() path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a> パス:: generic_string

すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a> パス:: generic_u16string

すべての円記号がスラッシュに変換された `u16string()` を返します (Windows の場合)。

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a> パス:: generic_u32string

すべての円記号がスラッシュに変換された `u32string()` を返します (Windows の場合)。

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a> パス:: generic_u8string

すべての円記号がスラッシュに変換された `u8string()` を返します (Windows の場合)。

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a> パス:: generic_wstring

すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a> パス:: has_extension

`!extension().empty()` を返します。

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a> パス:: has_filename

`!filename().empty()` を返します。

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a> パス:: has_parent_path

`!parent_path().empty()` を返します。

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a> パス:: has_relative_path

`!relative_path().empty()` を返します。

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a> パス:: has_root_directory

`!root_directory().empty()` を返します。

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a> パス:: has_root_name

`!root_name().empty()` を返します。

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a> パス:: has_root_path

`!root_path().empty()` を返します。

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a> パス:: has_stem

`!stem().empty()` を返します。

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a> パス:: is_absolute

Windows の場合、関数はを返し `has_root_name() && has_root_directory()` ます。 POSIX の場合、関数はを返し `has_root_directory()` ます。

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a> パス:: is_relative

`!is_absolute()` を返します。

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a> path:: iterator

のパスコンポーネントを指定する双方向定数反復子 `myname` 。

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

### <a name="remarks"></a>注釈

クラスは、 `path` シーケンス内ののコンポーネントを指定する双方向定数反復子を表し `myname` ます。

1. ルート名 (存在する場合)

1. ルート ディレクトリ (存在する場合)

1. 親の残りのディレクトリ要素 (存在する場合) (存在する場合)。 `path`

`pval`次の型のオブジェクトの場合 `path` :

1. `path::iterator X = pval.begin()` パス名の最初の `path` 要素 (存在する場合) を指定します。

1. `X == pval.end()` は、が `X` コンポーネントのシーケンスの末尾を越えた直後にある場合に true になります。

1. `*X` 現在のコンポーネントと一致する文字列を返します。

1. `++X` は、シーケンス内に次のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. `--X` は、シーケンス内に前のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. を変更すると `myname` 、の要素を指定するすべての反復子が無効に `myname` なります。

## <a name="pathmake_preferred"></a><a name="make_preferred"></a> パス:: make_preferred

必要に応じて、各区切り記号をに変換し `preferred_separator` ます。

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a> パス:: native

`myname` を返します。

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a> path:: operator =

パスの要素を別のパスのコピーで置き換えます。

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*そうです*\
にコピーされる [パス](../standard-library/path-class.md) `path` 。

*電源*\
ソースパス。

### <a name="remarks"></a>注釈

最初のメンバー演算子は、 `right.myname` をにコピーし `myname` ます。 2番目のメンバー演算子は、 `right.myname` に移動 `myname` します。 3番目のメンバー演算子はと同じように動作し `*this = path(source)` ます。

## <a name="pathoperator"></a><a name="op_add"></a> path:: operator + =

さまざまな `concat` 式。

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

*そうです*\
追加されたパス。

*引数*\
追加された文字列。

*ポインター*\
追加されたポインター。

*elem*\
追加 `value_type` または `Elem` 。

*電源*\
追加されたソース。

### <a name="remarks"></a>注釈

このメンバー関数には、次の対応する式と同じ効果があります。

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="pathoperator"></a><a name="op_divide"></a> path:: operator/=

さまざまな `append` 式。

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*そうです*\
追加されたパス。

*電源*\
追加されたソース。

### <a name="remarks"></a>注釈

このメンバー関数には、次の対応する式と同じ効果があります。

1. `append(right);`

1. `append(source);`

## <a name="pathoperator-string_type"></a><a name="op_string"></a> path:: operator string_type

`myname` を返します。

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a> パス::p arent_path

の親パスコンポーネントを返し `myname` ます。

```cpp
path parent_path() const;
```

### <a name="remarks"></a>注釈

の親パスコンポーネントを返し `myname` ます。具体的には、を `myname` 削除した後ののプレフィックス `filename().native()` と、直前のディレクトリ区切り記号を返します。 (同様に、場合によっては、 `begin() != end()` 範囲内のすべての要素を組み合わせ `[begin(), --end())` て適用 `operator/=` します)。コンポーネントが空である可能性があります。

## <a name="pathpath"></a><a name="path"></a> パス::p a

は、 `path` さまざまな方法でを構築します。

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

*そうです*\
構築されたパスがコピーされるパス。

*電源*\
構築されたパスがコピーされるソース。

*loc*\
指定されたロケール。

*まずは*\
コピーされる最初の要素の位置。

*前の*\
コピーされる最後の要素の位置。

### <a name="remarks"></a>注釈

コンストラクターはすべて、 `myname` 次のようにさまざまな方法で構成されます。

の場合 `path()` は `myname()` です。

の場合 `path(const path& right` ) です `myname(right.myname)` 。

の場合 `path(path&& right)` は `myname(right.myname)` です。

の場合 `template<class Source> path(const Source& source)` は `myname(source)` です。

そのために `template<class Source> path(const Source& source, const locale& loc)` は `myname(source)` 、から必要な codecvt ファセットを取得 `loc` します。

の場合 `template<class InIt> path(InIt first, InIt last)` は `myname(first, last)` です。

そのために `template<class InIt> path(InIt first, InIt last, const locale& loc)` は `myname(first, last)` 、から必要な codecvt ファセットを取得 `loc` します。

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a> パス::p referred_separator

この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>注釈

Windows では、ほとんどのコンテキストで、L'/' の代用が許容されます。

## <a name="pathrelative_path"></a><a name="relative_path"></a> パス:: relative_path

の相対パスコンポーネントを返し `myname` ます。

```cpp
path relative_path() const;
```

### <a name="remarks"></a>注釈

の相対パスコンポーネントを返し `myname` ます。具体的には、を `myname` 削除した後ののサフィックス `root_path().native()` と、それ以降の冗長ディレクトリ区切り記号を返します。 このコンポーネントは、空になることもあります。

## <a name="pathremove_filename"></a><a name="remove_filename"></a> パス:: remove_filename

ファイル名を削除します。

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a> パス:: replace_extension

の拡張機能を置き換え `myname` ます。

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>パラメーター

*newext*\
新しい拡張機能。

### <a name="remarks"></a>注釈

最初に、からサフィックスを削除 `extension().native()` `myname` します。 `!newext.empty() && newext[0] != dot`( `dot` がの場合 `*path(".").c_str()` ) の場合 `dot` は、がに追加され `myname` ます。 その後、 *newext* がに追加され `myname` ます。

## <a name="pathreplace_filename"></a><a name="replace_filename"></a> パス:: replace_filename

ファイル名を置き換えます。

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>パラメーター

*pval*\
ファイル名のパス。

### <a name="remarks"></a>注釈

このメンバー関数は、次のコードを実行します。

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathroot_directory"></a><a name="root_directory"></a> パス:: root_directory

のルートディレクトリコンポーネントを返し `myname` ます。

```cpp
path root_directory() const;
```

### <a name="remarks"></a>注釈

このコンポーネントは、空になることもあります。

## <a name="pathroot_name"></a><a name="root_name"></a> パス:: root_name

のルート名コンポーネントを返し `myname` ます。

```cpp
path root_name() const;
```

### <a name="remarks"></a>注釈

このコンポーネントは、空になることもあります。

## <a name="pathroot_path"></a><a name="root_path"></a> パス:: root_path

のルートパスコンポーネントを返し `myname` ます。

```cpp
path root_path() const;
```

### <a name="remarks"></a>注釈

のルートパスコンポーネント (具体的には) を返し `myname` `root_name()`  /  `root_directory` ます。 このコンポーネントは、空になることもあります。

## <a name="pathstem"></a><a name="stem"></a> パス:: ステム

`stem`のコンポーネントを返し `myname` ます。

```cpp
path stem() const;
```

### <a name="remarks"></a>注釈

`stem`のコンポーネントを返し `myname` `filename().native()` ます。具体的には、末尾が `extension().native()` 削除されます。 このコンポーネントは、空になることもあります。

## <a name="pathstring"></a><a name="string"></a> path:: string

に格納されているシーケンスを変換 `mypath` します。

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>注釈

最初の (テンプレート) メンバー関数は、次のように、同じ方法で格納されているシーケンスを変換し `mypath` ます。

1. `string<char, Traits, Alloc>()` の `string()`

1. `string<wchar_t, Traits, Alloc>()` の `wstring()`

1. `string<char16_t, Traits, Alloc>()` の `u16string()`

1. `string<char32_t, Traits, Alloc>()` の `u32string()`

2番目のメンバー関数は、に格納されているシーケンスを、 `mypath` シーケンスのホストシステムが優先するエンコーディングに変換 **`char`** し、型のオブジェクトに格納して返し `string` ます。

## <a name="pathstring_type"></a><a name="string_type"></a> パス:: string_type

この型は `basic_string<value_type>` の同意語です。

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a> path:: swap

`swap(mypath, right.mypath)`を実行します。

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a> パス:: u16string

に格納されているシーケンスを `mypath` utf-16 に変換し、型のオブジェクトに格納して返し `u16string` ます。

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a> パス:: u32string

に格納されているシーケンスを `mypath` 32 utf-8 に変換し、型のオブジェクトに格納されているを返し `u32string` ます。

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a> パス:: u8string

に格納されているシーケンスを `mypath` utf-8 に変換し、型のオブジェクトに格納して返し `u8string` ます。

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a> パス:: value_type

この型は、 `path` ホストオペレーティングシステムによって優先される要素を表します。

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a> path:: wstring

に格納されているシーケンスを、 `mypath` シーケンスのホストシステムによって優先されるエンコーディングに変換 **`wchar_t`** し、型のオブジェクトに格納して返し `wstring` ます。

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
