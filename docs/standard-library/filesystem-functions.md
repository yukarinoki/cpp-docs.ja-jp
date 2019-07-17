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
ms.openlocfilehash: fa54a68d22bfabe1efa8ae3c78e7e3c9350fb950
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68240713"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 関数

これらの free 関数、 [ \<filesystem >](../standard-library/filesystem.md)ヘッダーは、パス、ファイル、シンボリック リンク、ディレクトリ、およびボリュームに関する変更とクエリの操作を実行します。 詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="absolute"></a> 絶対

```cpp
path absolute(const path& pval, const path& base = current_path());
```

対応する絶対パス名を返します*pval*パス名を基準とした`base`:

1. 場合`pval.has_root_name() && pval.has_root_directory()`返します*pval*します。

1. 場合`pval.has_root_name() && !pval.has_root_directory()`返します`pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  / `pval.relative_path()`します。

1. 場合`!pval.has_root_name() && pval.has_root_directory()`返します`absolute(base).root_name()`  /  *pval*します。

1. 場合`!pval.has_root_name() && !pval.has_root_directory()`返します`absolute(base)`  /  *pval*します。

## <a name="begin"></a> 開始

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

どちらの関数が返す*iter*します。

## <a name="canonical"></a> Canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

すべての関数は、絶対パス名を形成`pabs = absolute(pval, base)`(または`pabs = absolute(pval)`基本パラメーターなしのオーバー ロード)、手順の次の順序で正規の形式にサイズを小さきます。

1. パス コンポーネント`X`を`is_symlink(X)`は**true**は置き換え`read_symlink(X)`します。

1. パス コンポーネント`.`(ドットは前のパス コンポーネントで規定される現在のディレクトリ) が削除されます。

1. パス コンポーネントのすべてのペア`X` / `..` (ドット ドットは前のパス コンポーネントで規定される親ディレクトリ) が削除されます。

関数は戻ります`pabs`します。

## <a name="copy"></a> コピー

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

関数は、すべてコピーまたはリンクの 1 つまたは複数のファイル*から*に*に*の制御下で*opts*、として取得されます`copy_options::none`ありませんオーバーロード*opts*パラメーター。 *opts*を 1 つのみが格納されます。

- `skip_existing`、 `overwrite_existing`、または `update_existing`

- `copy_symlinks` または `skip_symlinks`

- `directories_only`、 `create_symlinks`、または `create_hard_links`

関数は、まず file_status 値を決定`f`の*から*と`t`の*に*:

- 場合`opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`、呼び出すことによって `symlink_status`

- 呼び出すことによって、それ以外の場合、 `status`

- それ以外の場合は、エラーを報告します。

場合`!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`エラーが報告される (し他に何もしないでください)。

の場合`is_symlink(f)`し。

- 場合`options & copy_options::skip_symlinks`、何の操作を行います。

- の場合`!exists(t)&& options & copy_options::copy_symlinks`、し`copy_symlink(from, to, opts)`します。

- それ以外の場合、エラーを報告します。

の場合`is_regular_file(f)`、し。

- 場合`opts & copy_options::directories_only`、何の操作を行います。

- の場合`opts & copy_options::create_symlinks`、し`create_symlink(to, from)`します。

- の場合`opts & copy_options::create_hard_links`、し`create_hard_link(to, from)`します。

- の場合`is_directory(f)`、し`copy_file(from, to`  / `from.filename(), opts)`します。

- それ以外の場合は `copy_file(from, to, opts)`。

の場合`is_directory(f) && (opts & copy_options::recursive || !opts)`、し。

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

## <a name="copy_file"></a> copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

関数は、おそらくすべてのファイルをコピー*から*に*に*の制御下で*opts*、として取得されます`copy_options::none`、オーバー ロードの*opts*パラメーター。 *opts*の 1 つだけを含めることは`skip_existing`、 `overwrite_existing`、または`update_existing`します。

場合`exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`ファイルが既に存在しているエラーとして報告されます。

の場合`!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`、内容と、ファイルの属性をコピーしよう*から*ファイル*に*します。 このコピーの試行が失敗すると、エラーが報告されます。

関数が返す**true**コピーが成功すると、それ以外の場合とが行われた場合**false**します。

## <a name="copy_symlink"></a> copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

場合`is_directory(from)`、関数呼び出し`create_directory_symlink(from, to)`します。 それ以外の場合、呼び出す`create_symlink(from, to)`します。

## <a name="create_directories"></a> create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

ようなパス名を\/b\/c 関数のディレクトリを作成と\/b ディレクトリを作成できるように、必要に応じて、\/b\/c に応じて。 返します**true**実際には、ディレクトリを作成する場合にのみ*pval*します。

## <a name="create_directory"></a> create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

関数は、ディレクトリを作成します。 *pval*に応じて。 のみ true を返します、ディレクトリを実際に作成かどうか*pval*、既存のファイルからのアクセス許可をコピーする場合*attr*、またはを使用して`perms::all`、オーバー ロードの*attr*パラメーター。

## <a name="create_directory_symlink"></a> create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

関数は、ディレクトリへのシンボリック リンクとしてリンクを作成します。*に*します。

## <a name="create_hard_link"></a> create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

関数は、ディレクトリまたはファイルへのハード リンクとしてリンクを作成します。*に*します。

## <a name="create_symlink"></a> create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

関数は、作成*リンク*ファイルへのシンボリック リンクとして*に*します。

## <a name="current_path"></a> current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

パラメーターのない関数*pval*現在のディレクトリのパス名を返します。 残りの関数では、現在のディレクトリを設定*pval*します。

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

最初の関数を返します`directory_iterator()`し、2 番目の関数を返します `recursive_directory_iterator()`

## <a name="equivalent"></a> 等価

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

関数が返す**true**場合にのみ*左*と*右*に同じファイルシステムのエンティティを選択します。

## <a name="exists"></a>  exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

最初の関数は `status_known && stat.type() != file_not_found` を返します。 2 番目と 3 番目の関数が返す`exists(status(pval))`します。

## <a name="file_size"></a> file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

関数は、選択したファイルのバイト単位のサイズを返します*pval*場合は、`exists(pval) && is_regular_file(pval)`およびファイルのサイズを特定できることができます。 それ以外の場合、エラーを報告し、返す`uintmax_t(-1)`します。

## <a name="hard_link_count"></a> hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

ハード リンクの数を返します*pval*、または\-エラーが発生した場合は 1 です。

## <a name="hash_value"></a> hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

ハッシュ値を返します`pval.native()`します。

## <a name="is_block_file"></a> is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::block` を返します。 関数を返します。 残りの`is_block_file(status(pval))`します。

## <a name="is_character_file"></a> is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::character` を返します。 関数を返します。 残りの`is_character_file(status(pval))`します。

## <a name="is_directory"></a> is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::directory` を返します。 関数を返します。 残りの`is_directory_file(status(pval))`します。

## <a name="is_empty"></a> is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

場合`is_directory(pval)`、関数を返します`directory_iterator(pval) == directory_iterator()`; 返します`file_size(pval) == 0`します。

## <a name="is_fifo"></a> is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::fifo` を返します。 関数を返します。 残りの`is_fifo(status(pval))`します。

## <a name="is_other"></a> is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::other` を返します。 関数を返します。 残りの`is_other(status(pval))`します。

## <a name="is_regular_file"></a> is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::regular` を返します。 関数を返します。 残りの`is_regular_file(status(pval))`します。

## <a name="is_socket"></a> is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::socket` を返します。 関数を返します。 残りの`is_socket(status(pval))`します。

## <a name="is_symlink"></a> is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

最初の関数は `stat.type() == file_type::symlink` を返します。 関数を返します。 残りの`is_symlink(status(pval))`します。

## <a name="last_write_time"></a> last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

最初の 2 つの関数の最終データ変更の時刻を返す*pval*、または`file_time_type(-1)`エラーが発生した場合。 最後の 2 つの関数の最終データ変更の時刻を設定する*pval*に*new_time*します。

## <a name="permissions"></a> アクセス許可

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

関数によって選択されたパス名のアクセス許可を設定する*pval*に`mask & perms::mask`の制御下で`perms & (perms::add_perms | perms::remove_perms)`します。 *マスク*の 1 つだけを含めることは`perms::add_perms`と`perms::remove_perms`します。

場合`mask & perms::add_perms`、関数では、アクセス許可を設定`status(pval).permissions() | mask & perms::mask`します。 の場合`mask & perms::remove_perms`、関数では、アクセス許可を設定`status(pval).permissions() & ~(mask & perms::mask)`します。 関数がアクセス許可を設定それ以外の場合、`mask & perms::mask`します。

## <a name="proximate"></a> 近接

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a> read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

関数はエラーを報告し、返す`path()`場合`!is_symlink(pval)`します。 それ以外の場合は、これらの関数はシンボリック リンクを格納している `path` 型のオブジェクトを返します。

## <a name="relative"></a> 相対

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a> 削除します。

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

関数が返す**true**場合にのみ`exists(symlink_status(pval))`され、ファイルが正常に削除します。 シンボリック リンク自体が削除されると、選択したファイルではありません。

## <a name="remove_all"></a> remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

場合*pval*ディレクトリで、関数の再帰的にすべてのディレクトリ エントリでは、そのエントリ自体を削除します。 それ以外の場合、関数を呼び出す`remove`します。 これらの関数は、正常に削除した要素の合計数を返します。

## <a name="rename"></a> 名前の変更

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

関数の名前を変更*から*に*に*します。 シンボリック リンク自体は、名前を変更すると、選択したファイルではありません。

## <a name="resize_file"></a> resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

関数は、ファイルのサイズを変更します。 `file_size(pval) == size`

## <a name="space"></a> 領域

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

関数によって選択されたボリュームに関する情報を返します*pval*、型の構造体で`space_info`します。 構造に含まれる`uintmax_t(-1)`の任意の値を決定することはできません。

## <a name="status"></a> 状態

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

パス名のステータス、ファイルの種類、および関連付けられている権限を返す*pval*します。 シンボリック リンク自体は検証しますが、ファイルを選択します。

## <a name="status_known"></a> status_known

```cpp
bool status_known(file_status stat) noexcept;
```

関数の戻り値 `stat.type() != file_type::none`

## <a name="swap"></a> スワップ

```cpp
void swap(path& left, path& right) noexcept;
```

関数の内容を交換する*左*と*右*します。

## <a name="symlink_status"></a> symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

パス名シンボリック リンクのステータス、ファイルの種類、および関連付けられている権限を返す*pval*します。 関数の動作と同じ`status(pval)`シンボリック リンクは、テスト自体は、ある点がファイルではなくが選択されます。

## <a name="system_complete"></a> system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

これらの関数は、ルート名に関連付けられた現在のディレクトリを必要に応じて考慮に入れた絶対パス名を返します。 \(関数が返す posix 場合`absolute(pval)`します。\)

## <a name="temp_directory_path"></a> temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

これらの関数は、一時ファイルの格納に適したディレクトリのパス名を返します。

## <a name="u8path"></a> u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

最初の関数の動作と同じ`path(source)`と 2 番目の関数の動作と同じ`path(first, last)`utf-8 として、どのようなファイル システムにエンコードされた char の要素のシーケンスを各ケースで選択したソースが取得される点を除きします。

## <a name="weakly_canonical"></a> weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
