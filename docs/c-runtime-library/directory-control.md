---
description: 詳細については、「ディレクトリコントロール」を参照してください。
title: ディレクトリ制御
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
ms.openlocfilehash: a4115fc127292916f6f5b013f75104ed5771e5ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321236"
---
# <a name="directory-control"></a>ディレクトリ制御

これらのルーチンは、ディレクトリ構造に関する情報にアクセスし、変更し、取得します。

## <a name="directory-control-routines"></a>ディレクトリ制御ルーチン

|ルーチンによって返される値|使用|
|-------------|---------|
|[_chdir、_wchdir](../c-runtime-library/reference/chdir-wchdir.md)|現在の作業ディレクトリを変更する|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|現在のドライブを変更する|
|[_getcwd、_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|既定のドライブの現在の作業ディレクトリを取得する|
|[_getdcwd、_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|指定のドライブの現在の作業ディレクトリを取得する|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|ディスク ドライブに関する情報を **_diskfree_t** 構造体に入力する。|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|現在の (既定の) ドライブを取得する|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|現在使用できるディスク ドライブを表すビットマスクを返す。|
|[_mkdir、_wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|新しいディレクトリを作成する|
|[_rmdir、_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|ディレクトリを削除します|
|[_searchenv、_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)、[_searchenv_s、_wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|指定のパスで特定のファイルを検索する|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
[ファイルの処理](../c-runtime-library/file-handling.md)<br/>
[システムコール](../c-runtime-library/system-calls.md)<br/>
