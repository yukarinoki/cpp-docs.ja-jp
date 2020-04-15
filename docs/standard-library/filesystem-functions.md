---
title: '&lt;filesystem&gt; 関数'
ms.date: 03/27/2019
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.openlocfilehash: f1b48ed6f533d4ccb5f9ef5e6dbcbd6e5cc4f7a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332049"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 関数

[\<ファイルシステム>](../standard-library/filesystem.md)ヘッダー内のこれらの自由な関数は、パス、ファイル、シンボリックリンク、ディレクトリ、およびボリュームに対する変更操作と照会操作を行います。 詳細とコード例については、「ファイル[システム ナビゲーション (C++)」](../standard-library/file-system-navigation.md)を参照してください。

## <a name="absolute"></a><a name="absolute"></a>絶対

```cpp
path absolute(const path& pval, const path& base = current_path());
```

この関数は、パス名に対する*pval*相対パスに`base`対応する絶対パス名を返します。

1. 関数`pval.has_root_name() && pval.has_root_directory()`が*pval*を返す場合

1. 関数`pval.has_root_name() && !pval.has_root_directory()`が`pval.root_name()` / `absolute(base).root_directory()` / 戻る`absolute(base).relative_path()`場合 / . `pval.relative_path()`

1. 関数`!pval.has_root_name() && pval.has_root_directory()`が`absolute(base).root_name()` / *pval*を返す場合

1. 関数`!pval.has_root_name() && !pval.has_root_directory()`が`absolute(base)` / *pval*を返す場合

## <a name="begin"></a><a name="begin"></a>開始

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

どちらの関数も*反復を*返します。

## <a name="canonical"></a><a name="canonical"></a>正規

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

関数はすべて絶対パス名`pabs = absolute(pval, base)`(または`pabs = absolute(pval)`基本パラメーターのないオーバーロード) を形成し、次の手順の順序で正規形式に縮小します。

1. true の`X`パス`is_symlink(X)`コンポーネント**true**はすべて`read_symlink(X)`に置き換えられます。

1. すべてのパスコンポーネント`.`(ドットは、以前のパスコンポーネントによって確立された現在のディレクトリ)が削除されます。

1. パスコンポーネント`X`/`..`のすべてのペア(ドットドットは、以前のパスコンポーネントによって確立された親ディレクトリ)が削除されます。

この関数は、`pabs`を返します。

## <a name="copy"></a><a name="copy"></a>コピー

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

この関数は *、opts*パラメーターを持たないオーバーロード*from*の場合と同じ`copy_options::none`である opts の*制御下にある*1 つ以上のファイルをコピーまたはリンク*する*可能性があります。 *オプトは、* 以下のうち、最も 1 つを含むものとします。

- `skip_existing`、`overwrite_existing`、または `update_existing`

- `copy_symlinks` または `skip_symlinks`

- `directories_only`、`create_symlinks`、または `create_hard_links`

関数は、最初に from `f` `t` *と*for に対するfile_status値を決定*します*。

- if`opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`を呼び出すことによって`symlink_status`

- それ以外の場合は、`status`

- それ以外の場合は、エラーを報告します。

場合`!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`、エラーを報告します (他には何もしません)。

それ以外の`is_symlink(f)`場合は、次のようになります。

- の`options & copy_options::skip_symlinks`場合は何もしません。

- それ以外の`!exists(t)&& options & copy_options::copy_symlinks`場合は`copy_symlink(from, to, opts)`、 が必要です。

- それ以外の場合は、エラーを報告します。

それ以外の`is_regular_file(f)`場合は、次のようになります。

- の`opts & copy_options::directories_only`場合は何もしません。

- それ以外の`opts & copy_options::create_symlinks`場合は`create_symlink(to, from)`、 が必要です。

- それ以外の`opts & copy_options::create_hard_links`場合は`create_hard_link(to, from)`、 が必要です。

- それ以外の`is_directory(f)`場合は`copy_file(from, to` / `from.filename(), opts)`、 が必要です。

- それ以外の場合は `copy_file(from, to, opts)`。

それ以外の`is_directory(f) && (opts & copy_options::recursive || !opts)`場合は、次のようになります。

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

それ以外の場合は、何もしません。

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

この関数は *、opts*パラメーター*from*を持たないオーバーロードの場合と同じ`copy_options::none`で、 から から opts の*制御下に*ファイルをコピー*する*可能性があります。 *オプトは*`skip_existing`、 、 、`overwrite_existing`または`update_existing`の 1 つを含む必要があります。

の`exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`場合は、ファイルが既に存在することをエラーとして報告します。

それ以外の`!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`場合は *、ファイルの*内容と属性を*ファイルに*コピーしようとします。 このコピーの試行が失敗すると、エラーが報告されます。

コピーが試行されて成功した場合、関数は**true**を返し、それ以外の場合は**false**を返します。

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

の`is_directory(from)`場合、関数は`create_directory_symlink(from, to)`を呼び出します。 それ以外の場合`create_symlink(from, to)`は、 を呼び出します。

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

\/b\/c などのパス名の場合、関数は必要に応じてディレクトリ\/a と b を作成し、\/必要\/に応じてディレクトリ a b を作成できるようにします。 実際にディレクトリ*pval*を作成した場合にのみ**true**が返されます。

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

この関数は、必要に応じてディレクトリ*pval を*作成します。 実際にディレクトリ*pval*を作成する場合にのみ true を返し、その場合は既存のファイル*attr*からアクセス許可をコピーするか`perms::all`*、attr*パラメータを持たないオーバーロードを使用します。

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ディレクトリへのシンボリックリンクとしてリンク*を作成します*。

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ディレクトリまたはファイルへのハードリンクとして リンク*を作成します*。

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ファイルへのシンボリックリンクとして*リンク**を作成します*。

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

*pval*パラメーターを持たない関数は、現行ディレクトリーのパス名を戻します。 残りの関数は現在のディレクトリを*pval*に設定します。

## <a name="end"></a><a name="end"></a>終わり

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

最初の関数が`directory_iterator()`戻り、2 番目の関数が戻ります`recursive_directory_iterator()`

## <a name="equivalent"></a><a name="equivalent"></a>相当

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

関数は、*左*と*右*が同じファイルシステムエンティティを選択した場合にのみ**true**を返します。

## <a name="exists"></a><a name="exists"></a>存在

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

最初の関数は `status_known && stat.type() != file_not_found` を返します。 2 番目と 3`exists(status(pval))`番目の関数は を返します。

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

この関数は、 *pval*で選択されたファイルのサイズをバイト`exists(pval) && is_regular_file(pval)`単位で返し、ファイルサイズを決定することができます。 それ以外の場合は、エラー`uintmax_t(-1)`を報告し、 を返します。

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

この関数は *、pval*のハード リンクの数\-を返します。

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

関数は、 のハッシュ値`pval.native()`を返します。

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::block` を返します。 残りの関数は`is_block_file(status(pval))`を返します。

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::character` を返します。 残りの関数は`is_character_file(status(pval))`を返します。

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::directory` を返します。 残りの関数は`is_directory_file(status(pval))`を返します。

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

の`is_directory(pval)`場合、関数は返`directory_iterator(pval) == directory_iterator()`します。それ以外の`file_size(pval) == 0`場合は、 を返します。

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::fifo` を返します。 残りの関数は`is_fifo(status(pval))`を返します。

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::other` を返します。 残りの関数は`is_other(status(pval))`を返します。

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::regular` を返します。 残りの関数は`is_regular_file(status(pval))`を返します。

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::socket` を返します。 残りの関数は`is_socket(status(pval))`を返します。

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::symlink` を返します。 残りの関数は`is_symlink(status(pval))`を返します。

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

最初の 2 つの関数は *、pval*の最後のデータ`file_time_type(-1)`変更の時刻を返すか、エラーが発生した場合に返します。 最後の 2 つの関数は *、pval*の最後のデータ変更の時刻を*new_time*に設定します。

## <a name="permissions"></a><a name="permissions"></a>アクセス 許可

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

この関数は *、pval*で選択されたパス名のアクセス`mask & perms::mask`権を`perms & (perms::add_perms | perms::remove_perms)`の制御下に設定します。 *マスク*は、せいぜい 1`perms::add_perms`個`perms::remove_perms`を含むものと.

の`mask & perms::add_perms`場合、関数はアクセス許可を`status(pval).permissions() | mask & perms::mask`に設定します。 それ以外の`mask & perms::remove_perms`場合、関数はアクセス許可を`status(pval).permissions() & ~(mask & perms::mask)`に設定します。 それ以外の場合、関数はアクセス`mask & perms::mask`許可を に設定します。

## <a name="proximate"></a><a name="proximate"></a>近接

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a><a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

関数はエラーを報告し、if`!is_symlink(pval)`を返します`path()`。 それ以外の場合は、これらの関数はシンボリック リンクを格納している `path` 型のオブジェクトを返します。

## <a name="relative"></a><a name="relative"></a>相対

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>削除

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

この関数は **、** ファイルが`exists(symlink_status(pval))`正常に削除された場合にのみ true を返します。 シンボリックリンク自体は削除され、選択したファイルは削除されません。

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

*pval*がディレクトリの場合、関数は再帰的にすべてのディレクトリ エントリを削除し、そのエントリ自体を削除します。 それ以外の場合、`remove`関数は を呼び出します。 これらの関数は、正常に削除した要素の合計数を返します。

## <a name="rename"></a><a name="rename"></a>変更

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

関数の名前は*から**にします*。 シンボリックリンク自体は、選択したファイルではなく名前が変更されます。

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

これらの関数は、ファイルのサイズを変更し、`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>スペース

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

この関数は、 *pval*で選択されたボリュームに関する情報を`space_info`、 型の構造体で返します。 この構造体には`uintmax_t(-1)`、決定できない値が含まれています。

## <a name="status"></a><a name="status"></a>ステータス

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

これらの関数は *、pval*に関連付けられたパス名の状態、ファイルの種類、およびアクセス許可を返します。 シンボリックリンク自体はテストされず、選択したファイルです。

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

関数は戻ります`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>スワップ

```cpp
void swap(path& left, path& right) noexcept;
```

この関数は *、左右*の*内容を交換*します。

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

これらの関数は *、pval*に関連付けられたパス名シンボリックリンクステータス、ファイルタイプ、およびアクセス権を返します。 関数は、シンボリックリンク`status(pval)`自体が選択したファイルではなく、テストされる点を除いて、同じように動作します。

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

これらの関数は、ルート名に関連付けられた現在のディレクトリを必要に応じて考慮に入れた絶対パス名を返します。 \(POSIX の場合、関数`absolute(pval)`は を返します。\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

これらの関数は、一時ファイルの格納に適したディレクトリのパス名を返します。

## <a name="u8path"></a><a name="u8path"></a>u8パス

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

最初の関数は同じ動作`path(source)`をし、2 番目の関数は、それぞれのケース`path(first, last)`で選択されたソースが UTF-8 としてエンコードされた char 要素のシーケンスとして取られる点を除いて、ファイルシステムと同じように動作します。

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
