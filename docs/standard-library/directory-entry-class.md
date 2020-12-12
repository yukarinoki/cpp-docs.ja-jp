---
description: '詳細情報: directory_entry クラス'
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
ms.openlocfilehash: a4a4b69e9f568c19eefae79554838fac5781f3f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324549"
---
# <a name="directory_entry-class"></a>directory_entry クラス

`*X` によって返されるオブジェクトを表します。*X* は、[directory_iterator](../standard-library/directory-iterator-class.md) または [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) です。

## <a name="syntax"></a>構文

```cpp
class directory_entry;
```

## <a name="remarks"></a>解説

このクラスは、[path](../standard-library/path-class.md) 型のオブジェクトを格納します。 格納できる `path` は、[path クラス](../standard-library/path-class.md)のインスタンスまたは `path` の派生型のインスタンスです。 また、2 つの [file_type](../standard-library/filesystem-enumerations.md#file_type) 値も格納します。1 つは格納されたファイル名の状態に関する既知の情報を表し、もう 1 つはファイル名のシンボリック リンクの状態に関する既知の情報を表します。

詳細とコード例については、「 [ファイルシステムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[directory_entry](#directory_entry)|既定のコンストラクターは想定どおりの動作をします。 4番目のコンストラクターは、 `mypath` *pval*、 `mystat` *stat_arg*、および symstat_arg に初期化し `mysymstat` ます。 |

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[assign](#assign)|このメンバー関数は、 *pval* to `mypath` 、 *stat* to `mystat` 、および *symstat* をに割り当て `mysymstat` ます。|
|[path](#path)|このメンバー関数は、`mypath` を返します。|
|[replace_filename](#replace_filename)|このメンバー関数は `mypath` 、 `mypath.parent_path()`  /  *pval*、 `mystat` *stat_arg*、および `mysymstat` に置き換え symstat_arg|
|[status](#status)|どちらのメンバー関数も、最初に変更された可能性があるもの `mystat` を返します。|
|[symlink_status](#symlink_status)|どちらのメンバー関数も、最初に変更された可能性があるもの `mysymstat` を返します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator! =](#op_neq)|別のリストのコピーでリストの要素を置き換えます。|
|[operator =](#op_as)|この既定のメンバー代入演算子は想定どおりに動作します。|
|[operator = =](#op_eq)|`mypath == right.mypath` が返されます。|
|[<演算子 ](#op_lt)|`mypath < right.mypath` が返されます。|
|[operator<=](#op_lteq)|`!(right < *this)` が返されます。|
|[>演算子 ](#op_gt)|`right < *this` が返されます。|
|[operator>=](#op_gteq)|`!(*this < right)` が返されます。|
|[演算子 const path_type&](#path_type)|`mypath` が返されます。|

## <a name="requirements"></a>要件

**ヘッダー:** \<試験的/ファイルシステム&gt;

**名前空間:** std::experimental::filesystem

## <a name="assign"></a><a name="assign"></a> 割り当てる

このメンバー関数は、 *pval* をに割り当て `mypath` 、に *stat_arg* し、 `mystat` *symstat_arg* をに割り当て `mysymstat` ます。

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*\
格納されているファイル名のパス。

*stat_arg*\
格納されているファイル名の状態。

*symstat_arg*\
格納されているファイル名のシンボリックリンクの状態。

## <a name="directory_entry"></a><a name="directory_entry"></a> directory_entry

既定のコンストラクターは想定どおりの動作をします。 4番目のコンストラクターは、 `mypath` *pval*、 `mystat` *stat_arg*、および symstat_arg に初期化し `mysymstat` ます。 

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*\
格納されているファイル名のパス。

*stat_arg*\
格納されているファイル名の状態。

*symstat_arg*\
格納されているファイル名のシンボリックリンクの状態。

## <a name="operator"></a><a name="op_neq"></a> operator! =

このメンバー関数は、`!(*this == right)` を返します。

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operator"></a><a name="op_as"></a> operator =

この既定のメンバー代入演算子は想定どおりに動作します。

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>パラメーター

*そうです*\
にコピーされる [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operator"></a><a name="op_eq"></a> operator = =

このメンバー関数は、`mypath == right.mypath` を返します。

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

このメンバー関数は、`mypath < right.mypath` を返します。

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operatorlt"></a><a name="op_lteq"></a> operator&lt;=

このメンバー関数は、`!(right < *this)` を返します。

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operatorgt"></a><a name="op_gt"></a> operator&gt;

このメンバー関数は、`right < *this` を返します。

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operatorgt"></a><a name="op_gteq"></a> operator&gt;=

このメンバー関数は、`!(*this < right)` を返します。

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>パラメーター

*そうです*\
と比較する [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` 。

## <a name="operator-const-path_type"></a><a name="path_type"></a> 演算子 const path_type&

このメンバー演算子は、 `mypath`を返します。

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a><a name="path"></a> 道

このメンバー関数は、`mypath` を返します。

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a><a name="replace_filename"></a> replace_filename

このメンバー関数は `mypath` 、 `mypath.parent_path()`  /  *pval*、 `mystat` *stat_arg*、および `mysymstat` に置き換え symstat_arg

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>パラメーター

*pval*\
格納されているファイル名のパス。

*stat_arg*\
格納されているファイル名の状態。

*symstat_arg*\
格納されているファイル名のシンボリックリンクの状態。

## <a name="status"></a><a name="status"></a> オンライン

どちらのメンバー関数も、最初に次のように変更される `mystat` 可能性があります。

1. の場合は `status_known(mystat)` 、何も実行しません。

1. それ以外の場合は `!status_known(mysymstat) && !is_symlink(mysymstat)` `mystat = mysymstat` 。

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>パラメーター

*c*\
ステータスエラーコード。

## <a name="symlink_status"></a><a name="symlink_status"></a> symlink_status

2つのメンバー関数は、最初に次のように変更される可能性があります。 `mysymstat` の場合は `status_known(mysymstat)` 、何も行われません。 それ以外の場合は `mysymstat = symlink_status(mypval)`。

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>パラメーター

*c*\
ステータスエラーコード。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem&gt;](../standard-library/filesystem.md)
