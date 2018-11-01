---
title: directory_entry クラス
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: c1b68aefd44d8f0ac60c36307dee93333d801bb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533823"
---
# <a name="directoryentry-class"></a>directory_entry クラス

`*X` によって返されるオブジェクトを表します。*X* は、[directory_iterator](../standard-library/directory-iterator-class.md) または [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) です。

## <a name="syntax"></a>構文

```cpp
class directory_entry;
```

## <a name="remarks"></a>Remarks

このクラスは、[path](../standard-library/path-class.md) 型のオブジェクトを格納します。 格納できる `path` は、[path クラス](../standard-library/path-class.md)のインスタンスまたは `path` の派生型のインスタンスです。 また、2 つの [file_type](../standard-library/filesystem-enumerations.md#file_type) 値も格納します。1 つは格納されたファイル名の状態に関する既知の情報を表し、もう 1 つはファイル名のシンボリック リンクの状態に関する既知の情報を表します。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[directory_entry](#directory_entry)|既定のコンストラクターは想定どおりの動作をします。 4 番目のコンス トラクターによって初期化`mypath`に*pval*、`mystat`に*stat_arg*、および`mysymstat`に*symstat_arg と置き換えます。* します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[assign](#assign)|メンバー関数は、代入*pval*に`mypath`、 *stat*に`mystat`、および*symstat*に`mysymstat`します。|
|[path](#path)|このメンバー関数は、`mypath` を返します。|
|[replace_filename](#replace_filename)|メンバー関数は、`mypath`で`mypath.parent_path()`  /  *pval*、`mystat`で*stat_arg*、および`mysymstat`で*symstat_arg と置き換えます。*|
|[status](#status)|両方のメンバー関数が返す`mystat`最初に変更される可能性があります。|
|[symlink_status](#symlink_status)|両方のメンバー関数が返す`mysymstat`最初に変更される可能性があります。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|別のリストのコピーでリストの要素を置き換えます。|
|[operator=](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator==](#op_eq)|`mypath == right.mypath` を返します。|
|[operator<](#op_lt)|`mypath < right.mypath` を返します。|
|[operator<=](#op_lteq)|`!(right < *this)` を返します。|
|[operator>](#op_gt)|`right < *this` を返します。|
|[operator>=](#op_gteq)|`!(*this < right)` を返します。|
|[operator const path_type &](#path_type)|`mypath` を返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**  \< /ファイル システムの実験&gt;

**名前空間:** std::experimental::filesystem

## <a name="assign"></a> 割り当てる

メンバー関数は、代入*pval*に`mypath`、 *stat_arg*に`mystat`、および*symstat_arg と置き換えます。* に`mysymstat`します。

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
格納されているファイル名のパス。

*stat_arg*<br/>
格納されているファイル名の状態。

*symstat_arg と置き換えます。*<br/>
格納されているファイル名のシンボリック リンクの状態。

## <a name="directory_entry"></a> directory_entry

既定のコンストラクターは想定どおりの動作をします。 4 番目のコンス トラクターによって初期化`mypath`に*pval*、`mystat`に*stat_arg*、および`mysymstat`に*symstat_arg と置き換えます。* します。

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
格納されているファイル名のパス。

*stat_arg*<br/>
格納されているファイル名の状態。

*symstat_arg と置き換えます。*<br/>
格納されているファイル名のシンボリック リンクの状態。

## <a name="op_neq"></a> operator!=

このメンバー関数は、`!(*this == right)` を返します。

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="op_as"></a> 演算子 =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)にコピーされる、`directory_entry`します。

## <a name="op_eq"></a> 演算子 = =

このメンバー関数は、`mypath == right.mypath` を返します。

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="op_lt"></a> 演算子&lt;

このメンバー関数は、`mypath < right.mypath` を返します。

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="op_lteq"></a> 演算子&lt;=

このメンバー関数は、`!(right < *this)` を返します。

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="op_gt"></a> 演算子&gt;

このメンバー関数は、`right < *this` を返します。

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="op_gteq"></a> 演算子&gt;=

このメンバー関数は、`!(*this < right)` を返します。

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
[Directory_entry](../standard-library/directory-entry-class.md)と比較される、`directory_entry`します。

## <a name="path_type"></a> operator const path_type &

このメンバー演算子は、 `mypath`を返します。

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a> パス

このメンバー関数は、`mypath` を返します。

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a> replace_filename

メンバー関数は、`mypath`で`mypath.parent_path()`  /  *pval*、`mystat`で*stat_arg*、および`mysymstat`で*symstat_arg と置き換えます。*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*<br/>
格納されているファイル名のパス。

*stat_arg*<br/>
格納されているファイル名の状態。

*symstat_arg と置き換えます。*<br/>
格納されているファイル名のシンボリック リンクの状態。

## <a name="status"></a> 状態

両方のメンバー関数が返す`mystat`可能性がありますまずように変更します。

1. 場合`status_known(mystat)`し何も操作を行います。

1. の場合`!status_known(mysymstat) && !is_symlink(mysymstat)`し`mystat = mysymstat`します。

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>パラメーター

*ec*<br/>
状態エラー コード。

## <a name="symlink_status"></a> symlink_status

両方のメンバー関数が返す`mysymstat`可能性があります最初に変更される次のように: 場合`status_known(mysymstat)`し何も操作を行います。 それ以外の場合は `mysymstat = symlink_status(mypval)`。

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>パラメーター

*ec*<br/>
状態エラー コード。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem&gt;](../standard-library/filesystem.md)<br/>
