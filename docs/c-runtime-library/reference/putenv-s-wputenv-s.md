---
title: _putenv_s、_wputenv_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wputenv_s
- _putenv_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs:
- C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e84d7a68530a748c9b1ad7c553fad80ed4e7c86b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405576"
---
# <a name="putenvs-wputenvs"></a>_putenv_s、_wputenv_s

環境変数を作成、変更、または削除します。 これらのバージョンの [_putenv、_wputenv](putenv-wputenv.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _putenv_s(
   const char *varname,
   const char *value_string
);
errno_t _wputenv_s(
   const wchar_t *varname,
   const wchar_t *value_string
);
```

### <a name="parameters"></a>パラメーター

*varname*<br/>
環境変数名。

*value_string*<br/>
環境変数に設定する値。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*varname*|*value_string*|戻り値|
|------------|-------------|------------------|
|**NULL**|任意|**EINVAL**|
|任意|**NULL**|**EINVAL**|

いずれかのエラー条件が発生すると、これら関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EINVAL**設定と**errno**に**EINVAL**です。

## <a name="remarks"></a>コメント

**_Putenv_s**関数を新しい環境変数を追加または既存の環境変数の値を変更します。 環境変数は、プロセス (たとえば、プログラムにリンクされるライブラリの既定の検索パス) が実行される環境を定義します。 **_wputenv_s**のワイド文字バージョンは、 **_putenv_s**; *envstring*に渡す引数 **_wputenv_s**ワイド文字列です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname*を追加または変更する環境変数の名前を指定し、 *value_string*変数の値です。 場合*varname*は既に、環境の一部はその値に置き換え*value_string*以外の場合、新しい*varname*変数とその*value_string*環境に追加されます。 環境から変数を削除するには、空の文字列を指定することで (つまり、"") の*value_string*です。

**_putenv_s**と **_wputenv_s**現在のプロセスに対してローカルな環境のみに影響する以外の場合は、コマンド レベルの環境を変更するには使用できません。 これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体でのみ動作し、プロセス用にオペレーティング システムが作成する環境 "セグメント" では動作しません。 現在のプロセスが終了すると、環境は、呼び出し元プロセスのレベルに戻ります。これはほとんどの場合、オペレーティング システムのレベルです。 ただし、によって作成される新しいプロセスに変更された環境を渡すことができます **_spawn**、 **_exec**、または**システム**、し、これらの新しいプロセスである新しい項目を取得します。によって追加された **_putenv_s**と **_wputenv_s**です。

環境のエントリを直接変更しないでください。代わりに、 **_putenv_s**または **_wputenv_s**を変更します。 要素を具体的には、直接解放、 **_environ:operator[]** グローバル配列に対応する無効なメモリが発生する可能性があります。

**getenv**と **_putenv_s**グローバル変数を使用して **_environ**環境テーブルにアクセスするには **_wgetenv**と **_wputenv_s**使用 **_wenviron**です。 **_putenv_s**と **_wputenv_s**の値を変更することがあります **_environ**と **_wenviron**、それによってが無効になると、 *envp*に渡す引数**メイン**と **_wenvp**引数**wmain**です。 そのため、使用しても安全は **_environ**または **_wenviron**環境情報にアクセスします。 関係の詳細については **_putenv_s**と **_wputenv_s**グローバル変数に、次を参照してください。 [_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)です。

> [!NOTE]
> **_Putenv_s**と **_getenv_s**系関数はスレッド セーフではありません。 **_getenv_s**中に文字列ポインターを返すことが **_putenv_s**は、文字列を変更し、これはランダム エラーの原因です。 これらの関数の呼び出しが同期されていることを確認する必要があります。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

使用する方法を示すサンプルについて **_putenv_s**を参照してください[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)です。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv、 _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv、_wsearchenv](searchenv-wsearchenv.md)<br/>
