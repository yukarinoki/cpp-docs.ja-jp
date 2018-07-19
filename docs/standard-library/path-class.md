---
title: path クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8ea20d43e2679addc10465cfc549a64fc210274f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861689"
---
# <a name="path-class"></a>path クラス

**path** クラスとは、string\_type 型のオブジェクトを格納するクラスであり、パス名としての使用に適したクラスです。ここでは、このオブジェクトに myname という名前を付けて説明を進めます。 string\_type は、basic\_string\<value_type> のシノニムです。この value\_type は、Windows では char のシノニムになり、Posix では wchar_t のシノニムになります。

詳細およびコード例については、[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md) に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class path;
```

## <a name="pathappend"></a>path::append

```cpp
template <class Source>
path& append(const Source& source);

template <class InIt>
path& append(InIt first, InIt last);
```

これらのメンバー関数は、指定したシーケンスを mypath に追加します。必要に応じて変換と preferred_separator の挿入が行われます。

## <a name="pathassign"></a>path::assign

```cpp
template <class Source>
path& assign(const Source& source);

template <class InIt>
path& assign(InIt first, InIt last);
```

これらのメンバー関数は、指定したシーケンスで mypath を置き換えます。必要に応じて変換が行われます。

## <a name="pathbegin"></a>path::begin

```cpp
iterator begin() const;
```

パス名に含まれる最初のパス要素を指定している path::iterator を返します (存在する場合)。

## <a name="pathcstr"></a>path::c_str

```cpp
const value_type& *c_str() const noexcept;
```

mypath の最初の文字へのポインターを返します。

## <a name="pathclear"></a>path::clear

```cpp
void clear() noexcept;
```

このメンバー関数は、mypath.clear() を実行します。

## <a name="pathcompare"></a>path::compare

```cpp
int compare(const path& pval) const noexcept;
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```

最初の関数は、mypath.compare(pval.native()) を返します。 2 番目の関数は、mypath.compare(str) を返します。 3 番目の関数は、mypath.compare(ptr) を返します。

## <a name="pathconcat"></a>path::concat

```cpp
template <class Source>
path& concat(const Source& source);

template <class InIt>
path& concat(InIt first, InIt last);
```

これらのメンバー関数は、指定したシーケンスを mypath に追加します。必要に応じて変換が行われます (ただし、区切り記号の挿入は行われません)。

## <a name="pathconstiterator"></a>path::const_iterator

```cpp
typedef iterator const_iterator;
```

この型は、iterator のシノニムです。

## <a name="pathempty"></a>path::empty

```cpp
bool empty() const noexcept;
```

mypath.empty() を返します。

## <a name="pathend"></a>path::end

```cpp
iterator end() const;
```

シーケンスの最後の反復子 (iterator 型) を返します。

## <a name="pathextension"></a>path::extension

```cpp
path extension() const;
```

次に示すように、filename() X のサフィックスを返します。

X == path(".") &#124;&#124; X == path("..") の場合、または X にドットが含まれていない場合、サフィックスは空になります。

それ以外の場合、サフィックスは一番右にあるドットから始まります (このドットも含む)。

## <a name="pathfilename"></a>path::filename

```cpp
path filename() const;
```

myname のルート ディレクトリ コンポーネント (具体的には、 `empty()  path() : *--end()`」を参照してください。 このコンポーネントは、空になることもあります。

## <a name="pathgenericstring"></a>path::generic_string

```cpp
template <class Elem,
    class Traits = char_traits<Elem>,
    class Alloc = allocator<Elem>>
  basic_string<Elem, Traits, Alloc>
    generic_string(const Alloc& al = Alloc()) const;

string generic_string() const;
```

すべての円記号がスラッシュに変換された `this->string<Elem, Traits, Alloc>(al)` を返します (Windows の場合)。

## <a name="pathgenericu16string"></a>path::generic_u16string

```cpp
u16string generic_u16string() const;
```

すべての円記号がスラッシュに変換された u16string() を返します (Windows の場合)。

## <a name="pathgenericu32string"></a>path::generic_u32string

```cpp
u32string generic_u32string() const;
```

すべての円記号がスラッシュに変換された u32string() を返します (Windows の場合)。

## <a name="pathgenericu8string"></a>path::generic_u8string

```cpp
string generic_u8string() const;
```

すべての円記号がスラッシュに変換された u8string() を返します (Windows の場合)。

## <a name="pathgenericwstring"></a>path::generic_wstring

```cpp
wstring generic_wstring() const;
```

すべての円記号がスラッシュに変換された wstring() を返します (Windows の場合)。

## <a name="pathhasextension"></a>path::has_extension

```cpp
bool has_extension() const;
```

!extension().empty() を返します。

## <a name="pathhasfilename"></a>path::has_filename

```cpp
bool has_filename() const;
```

!filename().empty() を返します。

## <a name="pathhasparentpath"></a>path::has_parent_path

```cpp
bool has_parent_path() const;
```

!parent_path().empty() を返します。

## <a name="pathhasrelativepath"></a>path::has_relative_path

```cpp
bool has_relative_path() const;
```

!relative_path().empty() を返します。

## <a name="pathhasrootdirectory"></a>path::has_root_directory

```cpp
bool has_root_directory() const;
```

!root_directory().empty() を返します。

## <a name="pathhasrootname"></a>path::has_root_name

```cpp
bool has_root_name() const;
```

!root_name().empty() を返します。

## <a name="pathhasrootpath"></a>path::has_root_path

```cpp
bool has_root_path() const;
```

!root_path().empty() を返します。

## <a name="pathhasstem"></a>path::has_stem

```cpp
bool has_stem() const;
```

!stem().empty() を返します。

## <a name="pathisabsolute"></a>path::is_absolute

```cpp
bool is_absolute() const;
```

Windows の場合、この関数は has_root_name() && has_root_directory() を返します。 Posix の場合、この関数は has_root_directory() を返します。

## <a name="pathisrelative"></a>path::is_relative

```cpp
bool is_relative() const;
```

!is_absolute() を返します。

## <a name="pathiterator"></a>path::iterator

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

このクラスは、シーケンスに含まれる myname のパス コンポーネントを指定する、双方向の定数反復子を表します。

1. ルート名 (存在する場合)

1. ルート ディレクトリ (存在する場合)

1. 親パスの残りのディレクトリ要素 (存在する場合)。この要素の最後は、ファイル名になります (存在する場合)。

pval が path 型のオブジェクトの場合は、次のようになります。

1. path::iterator X = pval.begin() は、pathname に含まれる最初のパス要素を指定します (存在する場合)。

1. X == pval.end() は、X がコンポーネント シーケンスの末尾の直後をポイントしたときに true になります。

3. *X は、現在のコンポーネントと一致する文字列を返します。

1. ++X は、シーケンス内で次のコンポーネントを指定します (存在する場合)。

1. --X は、シーケンス内で前のコンポーネントを指定します (存在する場合)。

1. myname 変更すると、myname 内の要素を指定している、すべての反復子が無効になります。

## <a name="pathmakepreferred"></a>path::make_preferred

```cpp
path& make_preferred();
```

このメンバー関数は、区切り記号を必要に応じて preferred_separator に変換します。

## <a name="pathnative"></a>path::native

```cpp
const string_type& native() const noexcept;
```

myname を返します。

## <a name="pathoperator"></a>path::operator=

```cpp
path& operator=(const path& right);
path& operator=(path&& right) noexcept;

template <class Source>
path& operator=(const Source& source);
```

最初のメンバー演算子は、right.myname を myname にコピーします。 2 番目のメンバー演算子は、right.myname を myname に移動します。 3 番目のメンバー演算子は、*this = path(source) と同じ効果があります。

## <a name="pathoperator"></a>path::operator+=

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

このメンバー関数には、次の対応する式と同じ効果があります。

1. concat(right);

1. concat(path(str));

1. concat(ptr);

1. concat(string_type(1, elem));

1. concat(source);

1. concat(path(basic_string\<Elem>(1, elem)));

## <a name="pathoperator"></a>path::operator/=

```cpp
path& operator/=(const path& right);

template <class Source>
path& operator/=(const Source& source);
```

このメンバー関数には、次の対応する式と同じ効果があります。

1. append(right);

1. append(source);

## <a name="pathoperator-stringtype"></a>path::operator string_type

```cpp
operator string_type() const;
```

このメンバー演算子は、myname を返します。

## <a name="pathparentpath"></a>path::parent_path

```cpp
path parent_path() const;
```

myname の親パスのコンポーネントを返します。具体的には、filename().native() を削除した後の myname のプレフィックスと、その直前にあるディレクトリ区切り記号を返します (同様に、begin() != end() の場合、これは演算子 /= を連続して適用することによる範囲内 [begin(), --end()) のすべての要素の結合です。)このコンポーネントは、空になることもあります。

## <a name="pathpath"></a>path::path

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

これらすべてのコンストラクターは、さまざまな方法で myname を構築します。

path() の場合は、myname() になります。

path(const path& right) の場合は、myname(right.myname) になります。

path(path&& right) の場合は、myname(right.myname) になります。

template\<class Source> path(const Source& source) の場合は、myname(source) になります。

template\<class Source> path(const Source& source, const locale& loc) の場合は、必要な codecvt ファセットを loc から取得する、myname(source) になります。

template\<class InIt> path(InIt first, InIt last) の場合は、myname(first, last) になります。

template\<class InIt> path(InIt first, InIt last, const locale& loc) の場合は、必要な codecvt ファセットを loc から取得する、myname(first, last) になります。

## <a name="pathpreferredseparator"></a>path::preferred_separator

```cpp
#if _WIN32_C_LIB
static constexpr value_type preferred_separator == L'\\';
#else // assume Posix
static constexpr value_type preferred_separator == '/';
#endif // filesystem model now defined
```

この定数オブジェクトでは、パスのコンポーネントを区切るために推奨される文字を指定します。この文字は、ホスト オペレーティング システムによって異なります。 Windows では、ほとんどのコンテキストで、L'/' の代用が許容されます。

## <a name="pathrelativepath"></a>path::relative_path

```cpp
path relative_path() const;
```

myname の相対パス コンポーネントを返します。具体的には、root_path().native() と、その直後に続く余分なディレクトリ区切り文字を削除した後の myname のサフィックスを返します。 このコンポーネントは、空になることもあります。

## <a name="pathremovefilename"></a>path::remove_filename

```cpp
path& remove_filename();
```

## <a name="pathreplaceextension"></a>path::replace_extension

```cpp
path& replace_extension(const path& newext = path());
```

最初にメンバー関数により、サフィックス extension().native() が myname から削除されます。 その後、!newext.empty() && newext[0] != dot (dot は *path(".").c_str()) の場合は 、myname にドットが追加されます。 最後に、newext が myname に追加されます。

## <a name="pathreplacefilename"></a>path::replace_filename

```cpp
path& replace_filename(const path& pval);
```

このメンバー関数は、次のコードを実行します。

```cpp
remove_filename();

*this /= pval;
return (*this);
```

## <a name="pathrootdirectory"></a>path::root_directory

```cpp
path root_directory() const;
```

myname のルート ディレクトリ コンポーネントを返します。 このコンポーネントは、空になることもあります。

## <a name="pathrootname"></a>path::root_name

```cpp
path root_name() const;
```

myname のルート名コンポーネントを返します。 このコンポーネントは、空になることもあります。

## <a name="pathrootpath"></a>path::root_path

```cpp
path root_path() const;
```

myname のルート パス コンポーネントを返します。具体的には、root_name() または root_directory を返します。 このコンポーネントは、空になることもあります。

## <a name="pathstem"></a>path::stem

```cpp
path stem() const;
```

myname のステム コンポーネントを返します。具体的には、filename().native() から後続の extension().native() を削除したものを返します。 このコンポーネントは、空になることもあります。

## <a name="pathstring"></a>path::string

```cpp
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const;
string string() const;
```

最初の (テンプレート) メンバー関数は、mypath に格納されているシーケンスを次と同じ方法で変換します。

1. string\<char, Traits, Alloc>() の場合は string()

1. string\<wchar_t, Traits, Alloc>() の場合は wstring()

1. string\<char16_t, Traits, Alloc>() の場合は u16string()

1. string\<char32_t, Traits, Alloc>() の場合は u32string()

2 番目のメンバー関数は、mypath に格納されているシーケンスをホスト システムに適した char シーケンスのエンコーディングに変換してから、文字列型のオブジェクトに格納して返します。

## <a name="pathstringtype"></a>path::string_type

```cpp
typedef basic_string<value_type> string_type;
```

この型は、basic_string<value_type> のシノニムです。

## <a name="pathswap"></a>path::swap

```cpp
void swap(path& right) noexcept;
```

swap(mypath, right.mypath) を実行します。

## <a name="pathu16string"></a>path::u16string

```cpp
u16string u16string() const;
```

このメンバー関数は、mypath に格納されているシーケンスを UTF-16 に変換してから、u16string 型のオブジェクトに格納して返します。

## <a name="pathu32string"></a>path::u32string

```cpp
u32string u32string() const;
```

このメンバー関数は、mypath に格納されているシーケンスを UTF-32 に変換してから、u32string 型のオブジェクトに格納して返します。

## <a name="pathu8string"></a>path::u8string

```cpp
string u8string() const;
```

このメンバー関数は、mypath に格納されているシーケンスを UTF-8 に変換してから、u8string 型のオブジェクトに格納して返します。

## <a name="pathvaluetype"></a>path::value_type

```cpp
#if _WIN32_C_LIB
typedef wchar_t value_type;
#else // assume Posix
typedef char value_type;
#endif // filesystem model now defined
```

この型は、ホスト オペレーティング システムに適したパス要素を表します。

## <a name="pathwstring"></a>path::wstring

```cpp
wstring wstring() const;
```

mypath に格納されているシーケンスをホスト システムに適した wchar_t シーケンスのエンコーディングに変換してから、wstring 型のオブジェクトに格納して返します。

## <a name="requirements"></a>要件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
