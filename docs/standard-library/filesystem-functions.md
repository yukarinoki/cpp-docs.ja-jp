---
title: '&lt;filesystem&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: bfe07904a8eec87fb18441b92096d8ba6b72e4e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848662"
---
# <a name="ltfilesystemgt-functions"></a>&lt;filesystem&gt; 関数

[\<filesystem>](../standard-library/filesystem.md) ヘッダーに含まれるこれらの free 関数は、パス、ファイル、シンボリック リンク、およびディレクトリとボリュームの変更操作とクエリ操作を実行します。 詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」を参照してください。
||||
|-|-|-|
|[absolute](#absolute)|[begin](#begin)|[canonical](#canonical)|
|[copy](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[end](#end)|[equivalent](#equivalent)|[exists](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[permissions](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[rename](#rename)|
|[resize_file](#resize_file)|[space](#space)|[status](#status)|
|[status_known](#status_known)|[swap](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|


## <a name=""></a>  <a name="absolute"></a> absolute

```cpp
path absolute(const path& pval, const path& base = current_path());
```

この関数は、パス名 `base` を基準とする `pval` に対応する絶対パス名を以下のように返します。

1. pval.has_root_name() && pval.has_root_directory() の場合、この関数は pval を返します。

1. pval.has_root_name() && !pval.has_root_directory() の場合、この関数は pval.root_name() / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path() を返します。

1. !pval.has_root_name() && pval.has_root_directory() の場合、この関数は absolute(base).root_name() / pval を返します。

1. !pval.has_root_name() && !pval.has_root_directory() の場合、この関数は absolute(base) / pval を返します。

## <a name="begin"></a>  begin

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

どちらの関数も `iter` を返します。

## <a name="canonical"></a>  canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

これらすべての関数は、絶対パス名 pabs = absolute(pval, base) (base パラメーターを指定しないオーバーロードの場合は pabs = absolute(pval)) を形成してから、次に示す一連の手順で、その絶対パス名を標準の形式に短縮します。

1. is_symlink(X) が true のパス コンポーネント X は、すべて read_symlink(X) で置き換えられます。

1. パス コンポーネント . (ドットは、前のパス コンポーネントで規定される現在のディレクトリ) がすべて削除されます。

1. パス コンポーネント X/.. のペア (ドット ドットは、前のパス コンポーネントで規定される親ディレクトリ) がすべて削除されます。

このようにしてから、この関数は pabs を返します。

## <a name="copy"></a>  copy

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

これらすべての関数は、`opts` の制御下で `from` にある 1 つ以上のファイルを `to` にコピーまたはリンクします (可能な場合)。`opts` パラメーターを指定しないオーバーロードの場合、このパラメーターは copy_options::none と見なされます。 `opts` には、次のうちの 1 つのみが格納されます。

- skip_existing、overwrite_existing、または update_existing

- copy_symlinks または skip_symlinks

- directories_only、create_symlinks、または create_hard_links

これらの関数では、まず、`from` の file_status 値 f と `to` の file_status 値 t について、次のようにして判断します。

- opts & (copy_options::create_symlinks &#124; copy_options::skip_symlinks) が成立する場合は、symlink_status を呼び出します

- それ以外の場合は、status を呼び出します

- それ以外の場合は、エラーを報告します。

!exists(f) &#124;&#124; equivalent(f, t) &#124;&#124; is_other(f) &#124;&#124; is_other(t) &#124;&#124; is_directory(f)&& is_regular_file(t) が成立する場合は、エラーをレポートします (その他には何もしません)。

それ以外のときに is_symlink(f) が成立する場合:

- options & copy_options::skip_symlinks が成立する場合は何もしません。

- それ以外のときに !exists(t)&& options & copy_options::copy_symlinks が成立する場合は、copy_symlink(from, to, opts) を呼び出します。

- それ以外の場合は、エラーを報告します。

それ以外のときに is_regular_file(f) が成立する場合:

- opts & copy_options::directories_only が成立する場合は何もしません。

- それ以外のときに opts & copy_options::create_symlinks が成立する場合は、create_symlink(to, from) を呼び出します。

- それ以外のときに opts & copy_options::create_hard_links が成立する場合は、create_hard_link(to, from) を呼び出します。

- それ以外のときに is_directory(f) が成立する場合は、copy_file(from, to / from.filename(), opts) を呼び出します。

- それ以外の場合は、copy_file(from, to, opts) を呼び出します。

それ以外のときに is_directory(f) && (opts & copy_options::recursive &#124;&#124; !opts) が成立する場合:

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

## <a name="opy_file"></a>  copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

これらすべての関数は、`opts` の制御下で `from` にあるファイルを `to` にコピーします (可能な場合)。`opts` パラメーターを指定しないオーバーロードの場合、このパラメーターは copy_options::none と見なされます。 `opts` には、skip_existing、overwrite_existing、または update_existing のいずれか 1 つが格納されます。

exists\(to\) && \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\)\) が成立する場合は、既にファイルが存在しているというエラーが報告されます。

それ以外のときに \!exists\(to\) &#124;&#124; opts & copy_options::overwrite_existing &#124;&#124; opts & copy_options::update_existing&& last_write_time\(to\) \< last_write_time\(from\) &#124;&#124; \!\(opts & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options:update_existing\)\) が成立する場合は、ファイル from からファイル to への内容と属性のコピーが試行されます。 このコピーの試行が失敗すると、エラーが報告されます。

これらの関数は、コピーの試行が成功した場合は true を返します。それ以外の場合は、false を返します。

## <a name="copy_symlink "></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

is_directory\(from\) が成立する場合、この関数は create_directory_symlink\(from, to\) を呼び出します。 それ以外の場合は、create_symlink\(from, to\) を呼び出します。

## <a name="create_directories"></a>  create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

この関数は、a\/b\/c のようなパス名に対して、ディレクトリ a と a\/b を作成して (必要な場合)、ディレクトリ a\/b\/c を作成します (必要な場合)。 この関数は、ディレクトリ `pval` を実際に作成した場合にのみ true を返します。

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

この関数は、必要に応じてディレクトリ `pval` を作成します。 この関数は、ディレクトリ `pval` を実際に作成した場合にのみ true を返します。この場合、既存のファイル `attr` からアクセス許可がコピーされます。`attr` パラメーターを指定しないオーバーロードの場合は perms::all が使用されます。

## <a name="create_directory_symlink "></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ディレクトリ `to` へのリンクをシンボリック リンクとして作成します。

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ディレクトリまたはファイル `to` へのリンクをハード リンクとして作成します。

## <a name="create_symlink "></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

この関数は、ファイル `to` へのシンボリック リンクとして `link` を作成します。

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

これらの関数のうちパラメーターの `pval` がないものは、現在のディレクトリのパス名を返します。 それ以外の関数は、現在のディレクトリを `pval` に設定します。

## <a name="end"></a>  end

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

最初の関数は、directory_iterator\(\) を返します。2 番目の関数は、recursive_directory_iterator\(\) を返します。

## <a name="equivalent"></a>  equivalent

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

これらの関数は、`left` と `right` に同じファイルシステムのエンティティが指定されている場合にのみ true を返します。

## <a name="exists"></a>  exists

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

最初の関数は、status_known && stat.type\(\) \!\= file_not_found を返します。 2 番目の関数と 3 番目の関数は、exists\(status\(pval\)\) を返します。

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

これらの関数は、`pval` で指定されたファイルのサイズをバイト単位で返します (exists\(pval\) && is_regular_file\(pval\) が成立し、ファイルのサイズが判断できる場合)。 それ以外の場合は、エラーを報告して、uintmax_t\(\-1\) を返します。

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

この関数は、`pval` のハード リンクの数を返します。エラーが発生した場合は \-1 を返します。

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

この関数は、pval.native\(\) のハッシュ値を返します。

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::block を返します。 それ以外の関数は、is_block_file\(status\(pval\)\) を返します。

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::character を返します。 それ以外の関数は、is_character_file\(status\(pval\)\) を返します。

## <a name="is_directory "></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::directory を返します。 それ以外の関数は、is_directory_file\(status\(pval\)\) を返します。

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

is_directory\(pval\) が成立する場合、この関数は directory_iterator\(pval\) \=\= directory_iterator\(\) を返します。それ以外の場合は、file_size\(pval\) \=\= 0 を返します。

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::fifo を返します。 それ以外の関数は、is_fifo\(status\(pval\)\) を返します。

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::other を返します。 それ以外の関数は、is_other\(status\(pval\)\) を返します。

## <a name="s_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::regular を返します。 それ以外の関数は、is_regular_file\(status\(pval\)\) を返します。

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::socket を返します。 それ以外の関数は、is_socket\(status\(pval\)\) を返します。

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

最初の関数は、stat.type\(\) \=\= file_type::symlink を返します。 それ以外の関数は、is_symlink\(status\(pval\)\) を返します。

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

最初の 2 つの関数は、`pval` の最終データ変更の時刻を返します。エラーが発生した場合は、file_time_type\(\--1\) を返します。 残りの 2 つの関数は、`pval` の最終データ変更の時刻を new_time に設定します。

## <a name="permissions"></a>  permissions

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

これらの関数は、`pval` で指定したパス名のアクセス許可を perms & \(perms::add_perms &#124; perms::remove_perms\) の制御下で mask & perms::mask に設定します。 mask には、perms::add_perms と perms::remove_perms のいずれか 1 つのみが含まれます。

mask & perms::add_perms が成立する場合、これらの関数はアクセス許可を status\(pval\).permissions\(\) &#124; mask & perms::mask に設定します。 それ以外のときに mask & perms::remove_perms が成立する場合、この関数はアクセス許可を status\(pval\).permissions\(\) & ~\(mask & perms::mask\) に設定します。 それ以外の場合は、この関数はアクセス許可を mask & perms::mask に設定します。

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

これらの関数は、\!is_symlink\(pval\) が成立する場合にエラーを報告して path\(\) を返します。 それ以外の場合は、これらの関数はシンボリック リンクを格納している `path` 型のオブジェクトを返します。

## <a name="remove"></a>  remove

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

これらの関数は、exists\(symlink_status\(pval\)\) が成立していて、ファイルが正常に削除された場合にのみ true を返します。 シンボリック リンク自体が削除され、そのリンクが指定するファイルは削除されません。

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

`pval` がディレクトリの場合、これらの関数は、ディレクトリのエントリを再帰的にすべて削除してから、そのエントリ自体も削除します。 それ以外の場合、この関数は remove を呼び出します。 これらの関数は、正常に削除した要素の合計数を返します。

## <a name="rename"></a>  rename

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

これらの関数は、`from` から `to` に名前を変更します。 シンボリック リンク自体の名前が変更され、そのリンクが指定するファイルの名前は変更されません。

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

これらの関数は、file_size\(pval\) \=\= size にファイルのサイズを変更します。

## <a name="space"></a>  space

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

この関数は、`pval` で指定したボリュームに関する情報を `space_info` 型の構造体で返します。 この構造体では、判別できなかった値に対して uintmax_t\(\-1\) が格納されます。

## <a name="status"></a>  status

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

これらの関数は、`pval` に関連付けられたパス名のステータス、ファイルの種類およびアクセス許可を返します。 シンボリック リンク自体はテストされませんが、そのリンクが指定するファイルの名前はテストされます。

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

この関数は、stat.type\(\) \!\= file_type::none を返します。

## <a name="swap"></a>  swap

```cpp
void swap(path& left, path& right) noexcept;
```

この関数は、`left` と `right` の内容を交換します。

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

これらの関数は、`pval` に関連付けられたパス名シンボリック リンクのステータス、ファイルの種類およびアクセス許可を返します。 これらの関数は、status\(pval\) と同様に機能しますが、シンボリック リンク自体がテストされ、そのリンクが指定するファイルはテストされません。

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

これらの関数は、ルート名に関連付けられた現在のディレクトリを必要に応じて考慮に入れた絶対パス名を返します。 \(Posix 場合、この関数は absolute\(pval\) を返します\)。

## <a name="temp_directory_path"></a>  temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

これらの関数は、一時ファイルの格納に適したディレクトリのパス名を返します。

## <a name="u8path"></a>  u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

最初の関数は、path(source) と同じように機能し、2 番目の関数は、path(first, last) と同じように機能します。ただし、どちらの場合も、指定されたソースは、ファイルシステムに関係なく UTF-8 としてエンコードされた文字要素のシーケンスと見なされます。


