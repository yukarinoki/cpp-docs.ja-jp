---
title: path クラス
ms.date: 09/27/2018
f1_keywords:
- filesystem/std::experimental::filesystem::path
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
ms.openlocfilehash: 10c865aa2bc2431850c69e9dfedbef37414b2cb9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455095"
---
# <a name="path-class"></a>path クラス

**Path**クラスは、型`string_type`のオブジェクトを格納します。これは、パス名としての使用に適した、exposition の目的でここで呼び出され`myname`ます。 `string_type`はの`basic_string<value_type>`シノニムです。ここ`value_type`で、は、Windows の場合は**wchar_t** 、POSIX の場合は**char**です。

詳細およびコード例については、[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md) に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class path;
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[path](#path)|`path` を構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[const_iterator](#const_iterator)|`iterator` と同義。|
|[Iterator](#iterator)|`path` の`myname`コンポーネントを指定する双方向定数反復子。|
|[string_type](#string_type)|この型は `basic_string<value_type>` の同意語です。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[append](#append)|必要に応じて、 `mypath`指定したシーケンスをに追加し、preferred_separator に変換して挿入します。|
|[assign](#assign)|必要`mypath`に応じて変換された、指定したシーケンスで置き換えます。|
|[begin](#begin)|パス名`path::iterator`の最初のパス要素 (存在する場合) を示すを返します。|
|[c_str](#c_str)|の`mypath`最初の文字へのポインターを返します。|
|[clear](#clear)|を`mypath.clear()`実行します。|
|[compare](#compare)|比較値を返します。|
|[concat](#compare)|必要に応じて、 `mypath`指定したシーケンスをに追加します (区切り記号は挿入しません)。|
|[empty](#empty)|`mypath.empty()` を返します。|
|[end](#end)|型`iterator`のシーケンスの末尾の反復子を返します。|
|[extension](#extension)|の`filename()`サフィックスを返します。|
|[ファイル名](#filename)|myname のルート ディレクトリ コンポーネント (具体的には、 `empty() path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。|
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
|[is_absolute](#is_absolute)|Windows の場合、関数は`has_root_name() && has_root_directory()`を返します。 Posix の場合、関数は`has_root_directory()`を返します。|
|[is_relative](#is_relative)|`!is_absolute()` を返します。|
|[make_preferred](#make_preferred)|必要に応じて、各区切り記号を preferred_separator に変換します。|
|[native](#native)|`myname` を返します。|
|[parent_path](#parent_path)|の`myname`親パスコンポーネントを返します。|
|[preferred_separator](#preferred_separator)|この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。 |
|[relative_path](#relative_path)|の`myname`相対パスコンポーネントを返します。 |
|[remove_filename](#remove_filename)|ファイル名を削除します。|
|[replace_extension](#replace_extension)|の`myname`拡張機能を置き換えます。 |
|[replace_filename](#replace_filename)|ファイル名を置き換えます。|
|[root_directory](#root_directory)|の`myname`ルートディレクトリコンポーネントを返します。 |
|[root_name](#root_name)|の`myname`ルート名コンポーネントを返します。 |
|[root_path](#root_path)|の`myname`ルートパスコンポーネントを返します。|
|[生じ](#stem)|`stem` の`myname`コンポーネントを返します。|
|[string](#string)|に`mypath`格納されているシーケンスを変換します。|
|[swap](#swap)|を`swap(mypath, right.mypath)`実行します。|
|[u16string](#u16string)|に`mypath`格納されているシーケンスを utf-16 に変換し、型`u16string`のオブジェクトに格納して返します。|
|[u32string](#u32string)|に`mypath`格納されているシーケンスを 32 utf-8 に変換し、型`u32string`のオブジェクトに格納されているを返します。|
|[u8string](#u8string)|に`mypath`格納されているシーケンスを utf-8 に変換し、型`u8string`のオブジェクトに格納して返します。|
|[value_type](#value_type)|この型は、ホスト オペレーティング システムに適したパス要素を表します。|
|[wstring](#wstring)|に`mypath`格納されているシーケンスを、 `wchar_t`シーケンスのホストシステムによって優先されるエンコーディングに変換し、 `wstring`型のオブジェクトに格納して返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_as)|パスの要素を別のパスのコピーで置き換えます。|
|[operator+=](#op_add)|さまざま`concat`な式。|
|[operator/=](#op_divide)|さまざま`append`な式。|
|[string_type 演算子](#op_string)|`myname` を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<ファイルシステム >

**名前空間:** std::experimental::filesystem

## <a name="append"></a>path:: append

必要に応じて、 `mypath`指定したシーケンスを`preferred_separator`に追加し、変換して、挿入します。

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

## <a name="assign"></a>パス:: assign

必要`mypath`に応じて変換された、指定したシーケンスで置き換えます。

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

## <a name="begin"></a>path:: begin

パス名`path::iterator`の最初のパス要素 (存在する場合) を示すを返します。

```cpp
iterator begin() const;
```

## <a name="c_str"></a>パス:: c_str

の`mypath`最初の文字へのポインターを返します。

```cpp
const value_type& *c_str() const noexcept;
```

## <a name="clear"></a>パス:: clear

を`mypath.clear()`実行します。

```cpp
void clear() noexcept;
```

## <a name="compare"></a>path:: compare

最初の関数は `mypath.compare(pval.native())` を返します。 2 番目の関数は `mypath.compare(str)` を返します。 3番目の`mypath.compare(ptr)`関数はを返します。

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

## <a name="concat"></a>path:: concat

必要に応じて、 `mypath`指定したシーケンスをに追加します (区切り記号は挿入しません)。

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

## <a name="const_iterator"></a>パス:: const_iterator

`iterator` と同義。

```cpp
typedef iterator const_iterator;
```

## <a name="empty"></a>path:: empty

`mypath.empty()` を返します。

```cpp
bool empty() const noexcept;
```

## <a name="end"></a>パス:: 終了

型`iterator`のシーケンスの末尾の反復子を返します。

```cpp
iterator end() const;
```

## <a name="extension"></a>path:: extension

の`filename()`サフィックスを返します。

```cpp
path extension() const;
```

### <a name="remarks"></a>Remarks

次のような`filename() X`のサフィックスを返します。

にドットが含まれていない場合、サフィックスは空になります。 `X` `X == path(".") || X == path("..")`

それ以外の場合、サフィックスは一番右にあるドットから始まります (このドットも含む)。

## <a name="filename"></a>パス:: ファイル名

myname のルート ディレクトリ コンポーネント (具体的には、 `empty() path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。

```cpp
path filename() const;
```

## <a name="generic_string"></a>パス:: generic_string

すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

## <a name="generic_u16string"></a>パス:: generic_u16string

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

## <a name="generic_wstring"></a>パス:: generic_wstring

すべての円記号がスラッシュに変換された `wstring()` を返します (Windows の場合)。

```cpp
wstring generic_wstring() const;
```

## <a name="has_extension"></a>パス:: has_extension

`!extension().empty()` を返します。

```cpp
bool has_extension() const;
```

## <a name="has_filename"></a>パス:: has_filename

`!filename().empty()` を返します。

```cpp
bool has_filename() const;
```

## <a name="has_parent_path"></a>パス:: has_parent_path

`!parent_path().empty()` を返します。

```cpp
bool has_parent_path() const;
```

## <a name="has_relative_path"></a>パス:: has_relative_path

`!relative_path().empty()` を返します。

```cpp
bool has_relative_path() const;
```

## <a name="has_root_directory"></a>パス:: has_root_directory

`!root_directory().empty()` を返します。

```cpp
bool has_root_directory() const;
```

## <a name="has_root_name"></a>パス:: has_root_name

`!root_name().empty()` を返します。

```cpp
bool has_root_name() const;
```

## <a name="has_root_path"></a>パス:: has_root_path

`!root_path().empty()` を返します。

```cpp
bool has_root_path() const;
```

## <a name="has_stem"></a>パス:: has_stem

`!stem().empty()` を返します。

```cpp
bool has_stem() const;
```

## <a name="is_absolute"></a>パス:: is_absolute

Windows の場合、関数は`has_root_name() && has_root_directory()`を返します。 Posix の場合、関数は`has_root_directory()`を返します。

```cpp
bool is_absolute() const;
```

## <a name="is_relative"></a>パス:: is_relative

`!is_absolute()` を返します。

```cpp
bool is_relative() const;
```

## <a name="iterator"></a>path:: iterator

の`myname`パスコンポーネントを指定する双方向定数反復子。

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

クラスは、シーケンス内のの`path` `myname`コンポーネントを指定する双方向定数反復子を表します。

1. ルート名 (存在する場合)

1. ルート ディレクトリ (存在する場合)

1. 親`path`の残りのディレクトリ要素 (存在する場合) (存在する場合)。

次`pval`の型`path`のオブジェクトの場合:

1. `path::iterator X = pval.begin()`パス名の`path`最初の要素 (存在する場合) を指定します。

1. `X == pval.end()`は、が`X`コンポーネントのシーケンスの末尾を越えた直後にある場合に true になります。

3. `*X`現在のコンポーネントと一致する文字列を返します。

1. `++X` は、シーケンス内に次のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. `--X` は、シーケンス内に前のコンポーネントが存在する場合に、そのコンポーネントを指定します。

1. を`myname`変更すると、の要素`myname`を指定するすべての反復子が無効になります。

## <a name="make_preferred"></a>パス:: make_preferred

必要に応じて、 `preferred_separator`各区切り記号をに変換します。

```cpp
path& make_preferred();
```

## <a name="native"></a>パス:: native

`myname` を返します。

```cpp
const string_type& native() const noexcept;
```

## <a name="op_as"></a>path:: operator =

パスの要素を別のパスのコピーで置き換えます。

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

### <a name="parameters"></a>パラメーター

*そうです*\
に`path`コピーされる[パス](../standard-library/path-class.md)。

*電源*\
ソースパス。

### <a name="remarks"></a>Remarks

最初のメンバー演算子は`right.myname` 、 `myname`をにコピーします。 2番目のメンバー `right.myname`演算子`myname`は、に移動します。 3番目のメンバー演算子はと`*this = path(source)`同じように動作します。

## <a name="op_add"></a>path:: operator + =

さまざま`concat`な式。

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
追加`value_type`または`Elem`。

*電源*\
追加されたソース。

### <a name="remarks"></a>Remarks

このメンバー関数には、次の対応する式と同じ効果があります。

1. `concat(right);`

1. `concat(path(str));`

1. `concat(ptr);`

1. `concat(string_type(1, elem));`

1. `concat(source);`

1. `concat(path(basic_string<Elem>(1, elem)));`

## <a name="op_divide"></a>path:: operator/=

さまざま`append`な式。

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

### <a name="remarks"></a>Remarks

このメンバー関数には、次の対応する式と同じ効果があります。

1. `append(right);`

1. `append(source);`

## <a name="op_string"></a>path:: operator string_type

`myname` を返します。

```cpp
operator string_type() const;
```

## <a name="parent_path"></a>パス::p arent_path

の`myname`親パスコンポーネントを返します。

```cpp
path parent_path() const;
```

### <a name="remarks"></a>Remarks

の`myname`親パスコンポーネントを返します。具体的には`myname` 、を`filename().native()`削除した後ののプレフィックスと、直前のディレクトリ区切り記号を返します。 (同様に、 `begin() != end()`場合によっては、範囲`[begin(), --end())`内のすべての要素を組み合わせ`operator/=`て適用します)。このコンポーネントは、空になることもあります。

## <a name="path"></a>パス::p a

は、 `path`さまざまな方法でを構築します。

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

### <a name="remarks"></a>Remarks

コンストラクターはすべて、 `myname`次のようにさまざまな方法で構成されます。

の`path()`場合は`myname()`です。

の`path(const path& right`場合) `myname(right.myname)`です。

の`path(path&& right)`場合は`myname(right.myname)`です。

の`template<class Source> path(const Source& source)`場合は`myname(source)`です。

その`template<class Source> path(const Source& source, const locale& loc)`ために`myname(source)`は、から`loc`必要な codecvt ファセットを取得します。

の`template<class InIt> path(InIt first, InIt last)`場合は`myname(first, last)`です。

その`template<class InIt> path(InIt first, InIt last, const locale& loc)`ために`myname(first, last)`は、から`loc`必要な codecvt ファセットを取得します。

## <a name="preferred_separator"></a>パス::p referred_separator

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

## <a name="relative_path"></a>パス:: relative_path

の`myname`相対パスコンポーネントを返します。

```cpp
path relative_path() const;
```

### <a name="remarks"></a>Remarks

の`myname`相対パスコンポーネントを返します。具体的には`myname` 、を`root_path().native()`削除した後ののサフィックスと、それ以降の冗長ディレクトリ区切り記号を返します。 このコンポーネントは、空になることもあります。

## <a name="remove_filename"></a>パス:: remove_filename

ファイル名を削除します。

```cpp
path& remove_filename();
```

## <a name="replace_extension"></a>パス:: replace_extension

の`myname`拡張機能を置き換えます。

```cpp
path& replace_extension(const path& newext = path());
```

### <a name="parameters"></a>パラメーター

*newext*\
新しい拡張機能。

### <a name="remarks"></a>Remarks

最初に、から`extension().native()` `myname`サフィックスを削除します。 `!newext.empty() && newext[0] != dot` `dot` `myname`(がの場合)の場合は、がに追加されます。`*path(".").c_str()` `dot` その後、 *newext*が`myname`に追加されます。

## <a name="replace_filename"></a>パス:: replace_filename

ファイル名を置き換えます。

```cpp
path& replace_filename(const path& pval);
```

### <a name="parameters"></a>パラメーター

*pval*\
ファイル名のパス。

### <a name="remarks"></a>Remarks

このメンバー関数は、次のコードを実行します。

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="root_directory"></a>パス:: root_directory

の`myname`ルートディレクトリコンポーネントを返します。

```cpp
path root_directory() const;
```

### <a name="remarks"></a>Remarks

このコンポーネントは、空になることもあります。

## <a name="root_name"></a>パス:: root_name

の`myname`ルート名コンポーネントを返します。

```cpp
path root_name() const;
```

### <a name="remarks"></a>Remarks

このコンポーネントは、空になることもあります。

## <a name="root_path"></a>パス:: root_path

の`myname`ルートパスコンポーネントを返します。

```cpp
path root_path() const;
```

### <a name="remarks"></a>Remarks

の`myname`ルートパスコンポーネント (具体的`root_name()`  /  `root_directory`には) を返します。 このコンポーネントは、空になることもあります。

## <a name="stem"></a>パス:: ステム

`stem` の`myname`コンポーネントを返します。

```cpp
path stem() const;
```

### <a name="remarks"></a>Remarks

の`stem` `filename().native()` `extension().native()`コンポーネントを返します。具体的には、末尾が削除されます。 `myname` このコンポーネントは、空になることもあります。

## <a name="string"></a>path:: string

に`mypath`格納されているシーケンスを変換します。

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

### <a name="remarks"></a>Remarks

最初の (テンプレート) メンバー関数は、次のよう`mypath`に、同じ方法で格納されているシーケンスを変換します。

1. `string()` の `string<char, Traits, Alloc>()`

1. `wstring()` の `string<wchar_t, Traits, Alloc>()`

1. `u16string()` の `string<char16_t, Traits, Alloc>()`

1. `u32string()` の `string<char32_t, Traits, Alloc>()`

2番目のメンバー関数は、に`mypath`格納されているシーケンスを、 **char**シーケンスのホストシステムで優先されるエンコーディングに変換`string`し、型のオブジェクトに格納して返します。

## <a name="string_type"></a>パス:: string_type

この型は `basic_string<value_type>` の同意語です。

```cpp
typedef basic_string<value_type> string_type;
```

## <a name="swap"></a>path:: swap

を`swap(mypath, right.mypath)`実行します。

```cpp
void swap(path& right) noexcept;
```

## <a name="u16string"></a>パス:: u16string

に`mypath`格納されているシーケンスを utf-16 に変換し、型`u16string`のオブジェクトに格納して返します。

```cpp
u16string u16string() const;
```

## <a name="u32string"></a>パス:: u32string

に`mypath`格納されているシーケンスを 32 utf-8 に変換し、型`u32string`のオブジェクトに格納されているを返します。

```cpp
u32string u32string() const;
```

## <a name="u8string"></a>パス:: u8string

に`mypath`格納されているシーケンスを utf-8 に変換し、型`u8string`のオブジェクトに格納して返します。

```cpp
string u8string() const;
```

## <a name="value_type"></a>パス:: value_type

この型は、 `path`ホストオペレーティングシステムによって優先される要素を表します。

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

## <a name="wstring"></a>path:: wstring

に`mypath`格納されているシーケンスをホストシステムが使用する**wchar_t**シーケンスのエンコーディングに変換し、それを型`wstring`のオブジェクトに格納して返します。

```cpp
wstring wstring() const;
```

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
