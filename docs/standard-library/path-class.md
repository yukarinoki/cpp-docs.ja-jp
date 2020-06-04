---
title: path クラス
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 669dfd2c8cd8576ebfb6684bab7cf63cdd51babc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372104"
---
# <a name="path-class"></a>path クラス

**パス**クラスは、ここで呼び出`string_type`される、`myname`博覧会のために呼ばれる型のオブジェクトを格納し、パス名として使用するのに適しています。 `string_type`は、`basic_string<value_type>`の同義`value_type`語で、 Windows 上の**wchar_t**の同義語、または POSIX の**文字**です。

詳細およびコード例については、[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md) に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class path;
```

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[path](#path)|`path` を構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[const_iterator](#const_iterator)|`iterator` と同義。|
|[反復 子](#iterator)|の`path`コンポーネントを指定する双方向の定数反復器`myname`。|
|[string_type](#string_type)|この型は `basic_string<value_type>` の同意語です。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[追加](#append)|指定したシーケンスを に`mypath`追加し、必要に応じてpreferred_separatorを挿入します。|
|[割り当てる](#assign)|指定した`mypath`シーケンスで置換され、必要に応じて変換されます。|
|[開始](#begin)|パス名`path::iterator`の最初のパス要素を指定する場合は、返します。|
|[c_str](#c_str)|の最初の文字へのポインターを`mypath`返します。|
|[クリア](#clear)|を`mypath.clear()`実行します。|
|[比較](#compare)|比較値を返します。|
|[concat](#compare)|指定したシーケンスをに追加`mypath`します ( 必要に応じて変換 (区切り記号は挿入しません) 。|
|[empty](#empty)|`mypath.empty()` が返されます。|
|[end](#end)|型のシーケンス終了反復器を返します`iterator`。|
|[拡張子](#extension)|のサフィックスを`filename()`返します。|
|[Filename](#filename)|myname のルート ディレクトリ コンポーネント (具体的には、 `empty() path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。|
|[generic_string](#generic_string)|すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。|
|[generic_u16string](#generic_u16string)|すべての円記号がスラッシュに変換された `u16string()` を返します (Windows の場合)。|
|[generic_u32string](#generic_u32string)|すべての円記号がスラッシュに変換された `u32string()` を返します (Windows の場合)。|
|[generic_u8string](#generic_u8string)|すべての円記号がスラッシュに変換された `u8string()` を返します (Windows の場合)。|
|[generic_wstring](#generic_wstring)|すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。|
|[has_extension](#has_extension)|`!extension().empty()` が返されます。|
|[has_filename](#has_filename)|`!filename().empty()` が返されます。|
|[has_parent_path](#has_parent_path)|`!parent_path().empty()` が返されます。|
|[has_relative_path](#has_relative_path)|`!relative_path().empty()` が返されます。|
|[has_root_directory](#has_root_directory)|`!root_directory().empty()` が返されます。|
|[has_root_name](#has_root_name)|`!root_name().empty()` が返されます。|
|[has_root_path](#has_root_path)|`!root_path().empty()` が返されます。|
|[has_stem](#has_stem)|`!stem().empty()` が返されます。|
|[is_absolute](#is_absolute)|Windows の場合、関数`has_root_name() && has_root_directory()`は を返します。 POSIX の場合、関数`has_root_directory()`は を返します。|
|[is_relative](#is_relative)|`!is_absolute()` が返されます。|
|[make_preferred](#make_preferred)|必要に応じて、各区切り記号をpreferred_separatorに変換します。|
|[ネイティブ](#native)|`myname` が返されます。|
|[parent_path](#parent_path)|の親パス コンポーネントを`myname`返します。|
|[preferred_separator](#preferred_separator)|この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。 |
|[relative_path](#relative_path)|の相対パス コンポーネントを`myname`返します。 |
|[remove_filename](#remove_filename)|ファイル名を削除します。|
|[replace_extension](#replace_extension)|の`myname`拡張子を置き換えます。 |
|[replace_filename](#replace_filename)|R ファイル名を置き換えます。|
|[root_directory](#root_directory)|のルート ディレクトリ コンポーネント`myname`を返します。 |
|[root_name](#root_name)|のルート名コンポーネントを`myname`返します。 |
|[root_path](#root_path)|のルート パス コンポーネント`myname`を返します。|
|[stem](#stem)|のコンポーネント`stem`を`myname`返します。|
|[string](#string)|に格納されているシーケンスを`mypath`変換します。|
|[スワップ](#swap)|を`swap(mypath, right.mypath)`実行します。|
|[u16string](#u16string)|に格納されているシーケンス`mypath`を UTF-16 に変換し、型のオブジェクトに格納`u16string`されたシーケンスを返します。|
|[u32文字列](#u32string)|に格納されているシーケンス`mypath`を UTF-32 に変換し、型のオブジェクトに格納`u32string`されたシーケンスを返します。|
|[u8文字列](#u8string)|に格納されているシーケンス`mypath`を UTF-8 に変換し、型のオブジェクトに格納`u8string`されたシーケンスを返します。|
|[Value_type](#value_type)|この型は、ホスト オペレーティング システムに適したパス要素を表します。|
|[wstring](#wstring)|に格納されているシーケンス`mypath`を、ホスト システムが指定した`wchar_t`シーケンスのエンコーディングに変換し、型のオブジェクトに格納されたを返`wstring`します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_as)|パスの要素を別のパスのコピーに置き換えます。|
|[演算子 +=](#op_add)|様々`concat`な表現。|
|[演算子/=](#op_divide)|様々`append`な表現。|
|[オペレータstring_type](#op_string)|`myname` が返されます。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<ファイルシステム>

**名前空間:** std::experimental::filesystem

## <a name="pathappend"></a><a name="append"></a>パス::追加

指定したシーケンスを に`mypath`追加し、必要に`preferred_separator`応じて 変換して挿入します。

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*ソース*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの終了。

## <a name="pathassign"></a><a name="assign"></a>パス::割り当て

指定した`mypath`シーケンスで置換され、必要に応じて変換されます。

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*ソース*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの終了。

## <a name="pathbegin"></a><a name="begin"></a>パス::開始

パス名`path::iterator`の最初のパス要素を指定する場合は、返します。

```cpp
iterator begin() const;
```

## <a name="pathc_str"></a><a name="c_str"></a>パス::c_str

の最初の文字へのポインターを`mypath`返します。

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="pathclear"></a><a name="clear"></a>パス::クリア

を`mypath.clear()`実行します。

```cpp
void clear() noexcept;
```

## <a name="pathcompare"></a><a name="compare"></a>パス::比較

最初の関数は `mypath.compare(pval.native())` を返します。 2 番目の関数は `mypath.compare(str)` を返します。 3 番目の`mypath.compare(ptr)`関数は、 を返します。

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

### <a name="parameters"></a>パラメーター

*Pval*\
比較するパス。

*Str*\
比較する文字列。

*Ptr*\
比較するポインター。

## <a name="pathconcat"></a><a name="concat"></a>パス::コンキャット

指定したシーケンスをに追加`mypath`します ( 必要に応じて変換 (区切り記号は挿入しません) 。

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

### <a name="parameters"></a>パラメーター

*ソース*\
指定されたシーケンス。

*まずは*\
指定されたシーケンスの開始。

*前の*\
指定されたシーケンスの終了。

## <a name="pathconst_iterator"></a><a name="const_iterator"></a>パス::const_iterator

`iterator` と同義。

```cpp
typedef iterator const_iterator;
```

## <a name="pathempty"></a><a name="empty"></a>パス::空

`mypath.empty()` が返されます。

```cpp
bool empty() const noexcept;
```

## <a name="pathend"></a><a name="end"></a>パス::終了

型のシーケンス終了反復器を返します`iterator`。

```cpp
iterator end() const;
```

## <a name="pathextension"></a><a name="extension"></a>パス::拡張子

のサフィックスを`filename()`返します。

```cpp
path extension() const;
```

### <a name="remarks"></a>解説

次のようなサフィックスを`filename() X`返します。

ドット`X == path(".") || X == path("..")`が含`X`まれている場合、またはドットが含まれている場合、接尾辞は空です。

それ以外の場合、サフィックスは一番右にあるドットから始まります (このドットも含む)。

## <a name="pathfilename"></a><a name="filename"></a>パス::ファイル名

myname のルート ディレクトリ コンポーネント (具体的には、 `empty() path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。

```cpp
path filename() const;
```

## <a name="pathgeneric_string"></a><a name="generic_string"></a>パス::generic_string

すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="pathgeneric_u16string"></a><a name="generic_u16string"></a>パス::generic_u16string

すべての円記号がスラッシュに変換された `u16string()` を返します (Windows の場合)。

```cpp
u16string generic_u16string() const;
```

## <a name="pathgeneric_u32string"></a><a name="generic_u32string"></a>パス::generic_u32string

すべての円記号がスラッシュに変換された `u32string()` を返します (Windows の場合)。

```cpp
u32string generic_u32string() const;
```

## <a name="pathgeneric_u8string"></a><a name="generic_u8string"></a>パス::generic_u8string

すべての円記号がスラッシュに変換された `u8string()` を返します (Windows の場合)。

```cpp
string generic_u8string() const;
```

## <a name="pathgeneric_wstring"></a><a name="generic_wstring"></a>パス::generic_wstring

すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。

```cpp
wstring generic_wstring() const;
```

## <a name="pathhas_extension"></a><a name="has_extension"></a>パス::has_extension

`!extension().empty()` が返されます。

```cpp
bool has_extension() const;
```

## <a name="pathhas_filename"></a><a name="has_filename"></a>パス::has_filename

`!filename().empty()` が返されます。

```cpp
bool has_filename() const;
```

## <a name="pathhas_parent_path"></a><a name="has_parent_path"></a>パス::has_parent_path

`!parent_path().empty()` が返されます。

```cpp
bool has_parent_path() const;
```

## <a name="pathhas_relative_path"></a><a name="has_relative_path"></a>パス::has_relative_path

`!relative_path().empty()` が返されます。

```cpp
bool has_relative_path() const;
```

## <a name="pathhas_root_directory"></a><a name="has_root_directory"></a>パス::has_root_directory

`!root_directory().empty()` が返されます。

```cpp
bool has_root_directory() const;
```

## <a name="pathhas_root_name"></a><a name="has_root_name"></a>パス::has_root_name

`!root_name().empty()` が返されます。

```cpp
bool has_root_name() const;
```

## <a name="pathhas_root_path"></a><a name="has_root_path"></a>パス::has_root_path

`!root_path().empty()` が返されます。

```cpp
bool has_root_path() const;
```

## <a name="pathhas_stem"></a><a name="has_stem"></a>パス::has_stem

`!stem().empty()` が返されます。

```cpp
bool has_stem() const;
```

## <a name="pathis_absolute"></a><a name="is_absolute"></a>パス::is_absolute

Windows の場合、関数`has_root_name() && has_root_directory()`は を返します。 POSIX の場合、関数`has_root_directory()`は を返します。

```cpp
bool is_absolute() const;
```

## <a name="pathis_relative"></a><a name="is_relative"></a>パス::is_relative

`!is_absolute()` が返されます。

```cpp
bool is_relative() const;
```

## <a name="pathiterator"></a><a name="iterator"></a>パス::反復器

のパス コンポーネントを指定する双方向定数反復器`myname`。

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

### <a name="remarks"></a>解説

このクラスは、シーケンス`path``myname`内のコンポーネントを指定する双方向定数反復器を記述します。

1. ルート名 (存在する場合)

1. ルート ディレクトリ (存在する場合)

1. 親`path`の残りのディレクトリ要素が存在する場合は、ファイル名で終わる場合は、そのファイル名が存在する場合

型`pval``path`のオブジェクトの場合:

1. `path::iterator X = pval.begin()`パス名の最初`path`の要素を指定します (存在する場合)。

1. `X == pval.end()`コンポーネントのシーケンス`X`の終わりが終わる直前のポイントの場合は true です。

1. `*X`現在のコンポーネントと一致する文字列を返します

1. `++X` は、シーケンス内に次のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. `--X` は、シーケンス内に前のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. 変更すると`myname`、 内`myname`の要素を指定するすべての反復子が無効になります。

## <a name="pathmake_preferred"></a><a name="make_preferred"></a>パス::make_preferred

必要に応じて各区切`preferred_separator`り記号をに変換します。

```cpp
path& make_preferred();
```

## <a name="pathnative"></a><a name="native"></a>パス::ネイティブ

`myname` が返されます。

```cpp
const string_type& native() const noexcept;
```

## <a name="pathoperator"></a><a name="op_as"></a>パス::演算子=

パスの要素を別のパスのコピーに置き換えます。

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*そうです*\
にコピーされる[パス](../standard-library/path-class.md)。 `path`

*ソース*\
ソース パス。

### <a name="remarks"></a>解説

最初のメンバ オペレータ`right.myname`は`myname`にコピーします。 2 番目のメンバ`right.myname`演算子`myname`は に移動します。 3 番目のメンバー演算子は、 と`*this = path(source)`同じように動作します。

## <a name="pathoperator"></a><a name="op_add"></a>パス::演算子+=

様々`concat`な表現。

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

*Str*\
追加された文字列。

*Ptr*\
追加されたポインター。

*Elem*\
追加された`value_type`または`Elem`.

*ソース*\
追加されたソース。

### <a name="remarks"></a>解説

このメンバー関数には、次の対応する式と同じ効果があります。

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="pathoperator"></a><a name="op_divide"></a>パス::演算子/=

様々`append`な表現。

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*そうです*\
追加されたパス。

*ソース*\
追加されたソース。

### <a name="remarks"></a>解説

このメンバー関数には、次の対応する式と同じ効果があります。

1. `append(right);`

1. `append(source);`

## <a name="pathoperator-string_type"></a><a name="op_string"></a>パス::演算子string_type

`myname` が返されます。

```cpp
operator string_type() const;
```

## <a name="pathparent_path"></a><a name="parent_path"></a>パス::pレント_パス

の親パス コンポーネントを`myname`返します。

```cpp
path parent_path() const;
```

### <a name="remarks"></a>解説

の親パス コンポーネント`myname`を`myname``filename().native()`返します。 (同様に、`begin() != end()`場合は、範囲内のすべての要素を連続的に適用`[begin(), --end())`することによって結合します`operator/=`。コンポーネントが空である可能性があります。

## <a name="pathpath"></a><a name="path"></a>パス::path

さまざまな方法で`path`を構築します。

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
構築されたパスがコピーになるパス。

*ソース*\
構築されたパスがコピーになるソース。

*Loc*\
指定したロケール。

*まずは*\
コピーされる最初の要素の位置。

*前の*\
コピーする最後の要素の位置。

### <a name="remarks"></a>解説

コンストラクターはすべて、さまざまな方法`myname`で構築します。

それは`path()`. `myname()`

)`path(const path& right`の場合`myname(right.myname)`は です。

それは`path(path&& right)`. `myname(right.myname)`

それは`template<class Source> path(const Source& source)`. `myname(source)`

の`template<class Source> path(const Source& source, const locale& loc)`は`myname(source)`、必要な codecvt ファセットを から`loc`取得することです。

それは`template<class InIt> path(InIt first, InIt last)`. `myname(first, last)`

の`template<class InIt> path(InIt first, InIt last, const locale& loc)`は`myname(first, last)`、必要な codecvt ファセットを から`loc`取得することです。

## <a name="pathpreferred_separator"></a><a name="preferred_separator"></a>パス::p参照_区切り記号

この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume POSIX
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

### <a name="remarks"></a>解説

Windows では、ほとんどのコンテキストで、L'/' の代用が許容されます。

## <a name="pathrelative_path"></a><a name="relative_path"></a>パス::relative_path

の相対パス コンポーネントを`myname`返します。

```cpp
path relative_path() const;
```

### <a name="remarks"></a>解説

の相対パス コンポーネント`myname`を返します。 `myname` `root_path().native()` このコンポーネントは、空になることもあります。

## <a name="pathremove_filename"></a><a name="remove_filename"></a>パス::remove_filename

ファイル名を削除します。

```cpp
path& remove_filename();
```

## <a name="pathreplace_extension"></a><a name="replace_extension"></a>パス::replace_extension

の`myname`拡張子を置き換えます。

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>パラメーター

*ニューエクスト*\
新しい拡張機能。

### <a name="remarks"></a>解説

まず、 から`extension().native()``myname`サフィックスを削除します。 次に`!newext.empty() && newext[0] != dot`、 `dot` (`*path(".").c_str()`が`dot`) されている`myname`場合は、 に追加されます。 その後 *、newext*が`myname`に追加されます。

## <a name="pathreplace_filename"></a><a name="replace_filename"></a>パス::replace_filename

ファイル名を置き換えます。

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>パラメーター

*Pval*\
ファイル名のパス。

### <a name="remarks"></a>解説

このメンバー関数は、次のコードを実行します。

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathroot_directory"></a><a name="root_directory"></a>パス::root_directory

のルート ディレクトリ コンポーネント`myname`を返します。

```cpp
path root_directory() const;
```

### <a name="remarks"></a>解説

このコンポーネントは、空になることもあります。

## <a name="pathroot_name"></a><a name="root_name"></a>パス::root_name

のルート名コンポーネントを`myname`返します。

```cpp
path root_name() const;
```

### <a name="remarks"></a>解説

このコンポーネントは、空になることもあります。

## <a name="pathroot_path"></a><a name="root_path"></a>パス::root_path

のルート パス コンポーネント`myname`を返します。

```cpp
path root_path() const;
```

### <a name="remarks"></a>解説

のルート パス コンポーネント`myname`を返`root_name()` / `root_directory`します。 このコンポーネントは、空になることもあります。

## <a name="pathstem"></a><a name="stem"></a>パス::茎

のコンポーネント`stem`を`myname`返します。

```cpp
path stem() const;
```

### <a name="remarks"></a>解説

のコンポーネント`stem`を返`myname`し、`filename().native()`特に末尾`extension().native()`を削除します。 このコンポーネントは、空になることもあります。

## <a name="pathstring"></a><a name="string"></a>パス::文字列

に格納されているシーケンスを`mypath`変換します。

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>解説

最初の (テンプレート) メンバー関数は、格納されている`mypath`シーケンスを次のように変換します。

1. `string<char, Traits, Alloc>()` の `string()`

1. `string<wchar_t, Traits, Alloc>()` の `wstring()`

1. `string<char16_t, Traits, Alloc>()` の `u16string()`

1. `string<char32_t, Traits, Alloc>()` の `u32string()`

2 番目のメンバー関数は、 に`mypath`格納されているシーケンスを **、 char**シーケンスのホスト システムが優先するエンコーディングに変換し、型`string`のオブジェクトに格納されたシーケンスを返します。

## <a name="pathstring_type"></a><a name="string_type"></a>パス::string_type

この型は `basic_string<value_type>` の同意語です。

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="pathswap"></a><a name="swap"></a>パス::スワップ

を`swap(mypath, right.mypath)`実行します。

```cpp
void swap(path& right) noexcept;
```

## <a name="pathu16string"></a><a name="u16string"></a>パス::u16文字列

に格納されているシーケンス`mypath`を UTF-16 に変換し、型のオブジェクトに格納`u16string`されたシーケンスを返します。

```cpp
u16string u16string() const;
```

## <a name="pathu32string"></a><a name="u32string"></a>パス::u32文字列

に格納されているシーケンス`mypath`を UTF-32 に変換し、型のオブジェクトに格納`u32string`されたシーケンスを返します。

```cpp
u32string u32string() const;
```

## <a name="pathu8string"></a><a name="u8string"></a>パス::u8文字列

に格納されているシーケンス`mypath`を UTF-8 に変換し、型のオブジェクトに格納`u8string`されたシーケンスを返します。

```cpp
string u8string() const;
```

## <a name="pathvalue_type"></a><a name="value_type"></a>パス::value_type

この型は、ホスト`path`オペレーティング システムが使用する要素を表します。

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume POSIX
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="pathwstring"></a><a name="wstring"></a>パス::wstring

に格納されているシーケンス`mypath`を **、ホスト**システムがwchar_t シーケンスに使用するエンコーディングに変換し、型のオブジェクトに格納されたを`wstring`返します。

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
