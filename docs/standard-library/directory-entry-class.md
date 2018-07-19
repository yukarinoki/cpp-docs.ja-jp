---
title: directory_entry クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 9a55109683a18415638cacd9cd15dbcaa3164fc8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846933"
---
# <a name="directoryentry-class"></a>directory_entry クラス

`*X` によって返されるオブジェクトを表します。*X* は、[directory_iterator](../standard-library/directory-iterator-class.md) または [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) です。

## <a name="syntax"></a>構文

```cpp
class directory_entry;
```

## <a name="remarks"></a>コメント

このクラスは、[path](../standard-library/path-class.md) 型のオブジェクトを格納します。 格納できる `path` は、[path クラス](../standard-library/path-class.md)のインスタンスまたは `path` の派生型のインスタンスです。 また、2 つの [file_type](../standard-library/filesystem-enumerations.md#file_type) 値も格納します。1 つは格納されたファイル名の状態に関する既知の情報を表し、もう 1 つはファイル名のシンボリック リンクの状態に関する既知の情報を表します。

詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="assign"></a>assign

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

このメンバー関数は、pval を mypath に、stat を mystat に、symstat を mysymstat に割り当てます。

## <a name="directoryentry"></a>directory_entry

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

既定のコンストラクターは想定どおりの動作をします。 4 番目のコンストラクターは、mypath を pval に、mystat を stat_arg に、mysymstat を symstat_arg に初期化します。

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

このメンバー関数は !(*this == right) を返します。

## <a name="operator"></a>operator=

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

この既定のメンバー代入演算子は想定どおりに動作します。

## <a name="operator"></a>operator==

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

このメンバー関数は mypath == right.mypath を返します。

## <a name="operatorlt"></a>演算子&lt;

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

このメンバー関数は mypath を返します&lt;right.mypath です。

## <a name="operatorlt"></a>operator&lt;=

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

このメンバー関数は !(right \< *this) を返します。

## <a name="operatorgt"></a>演算子&gt;

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

このメンバー関数は right \< *this を返します。

## <a name="operatorgt"></a>operator&gt;=

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

このメンバー関数を返します。(* この\<右)。

## <a name="operator-const-pathtype"></a>operator const path_type&

```cpp
operator const std::experimental::filesystem::path&() const;
```

このメンバー演算子は mypath を返します。

## <a name="path"></a>path

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

このメンバー関数は mypath を返します。

## <a name="replacefilename"></a>replace_filename

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

このメンバー関数は、mypath を mypath.parent_path() / pval、mystat を stat_arg、mysymstat を symstat_arg と置き換えます。

## <a name="status"></a>状態

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

メンバー関数はどちらも、恐らく最初に mystat を次のように変更し、それからこれを返します。

1. status_known(mystat) の場合は何も実行しません。

1. それ以外の場合は、!status_known(mysymstat) && !is_symlink(mysymstat) であれば mystat = mysymstat です。

## <a name="symlinkstatus"></a>symlink_status

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

メンバー関数ではどちらも、恐らく最初に mysymstat を次のように変更し、それからこれを返します。status_known(mysymstat) の場合は何もしません。 それ以外の場合、mysymstat = symlink_status(mypval) です。

## <a name="requirements"></a>要件

**ヘッダー:** \<実験/filesystem&gt;

**名前空間:** std::experimental::filesystem

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem&gt;](../standard-library/filesystem.md)<br/>
