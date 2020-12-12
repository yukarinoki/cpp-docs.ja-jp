---
description: '詳細については、次を参照してください: _putenv_s、_wputenv_s'
title: _putenv_s、_wputenv_s
ms.date: 4/2/2020
api_name:
- _wputenv_s
- _putenv_s
- _o__putenv_s
- _o__wputenv_s
api_location:
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
ms.openlocfilehash: bba9d595d716f3a8e5e9c41326a0258b10e8abf8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246293"
---
# <a name="_putenv_s-_wputenv_s"></a>_putenv_s、_wputenv_s

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
|**NULL**|any|**EINVAL**|
|any|**NULL**|**EINVAL**|

いずれかのエラー条件が発生すると、これら関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は **einval** を返し、 **errno** を **einval** に設定します。

## <a name="remarks"></a>解説

**_Putenv_s** 関数は、新しい環境変数を追加するか、既存の環境変数の値を変更します。 環境変数は、プロセス (たとえば、プログラムにリンクされるライブラリの既定の検索パス) が実行される環境を定義します。 **_wputenv_s** は **_putenv_s** のワイド文字バージョンです。**_wputenv_s** の *envstring* 引数は、ワイド文字列です。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tputenv_s**|**_putenv_s**|**_putenv_s**|**_wputenv_s**|

*varname* は、追加または変更する環境変数の名前です。 *value_string* 変数の値です。 *Varname* が既に環境の一部である場合、その値は *value_string*; に置き換えられます。それ以外の場合は、新しい *varname* 変数とその *value_string* が環境に追加されます。 環境から変数を削除するには、 *value_string* に空の文字列 ("") を指定します。

**_putenv_s** と **_wputenv_s** は、現在のプロセスに対してローカルな環境にのみ影響します。これらのコマンドを使用して、コマンドレベルの環境を変更することはできません。 これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体でのみ動作し、プロセス用にオペレーティング システムが作成する環境 "セグメント" では動作しません。 現在のプロセスが終了すると、環境は、呼び出し元プロセスのレベルに戻ります。これはほとんどの場合、オペレーティング システムのレベルです。 ただし、変更された環境は **_spawn**、 **_exec**、または **システム** によって作成された新しいプロセスに渡すことができ、これらの新しいプロセスは **_putenv_s** および **_wputenv_s** によって追加された新しい項目を取得します。

環境エントリを直接変更しないでください。代わりに、 **_putenv_s** または **_wputenv_s** を使用して変更してください。 特に、 **_environ []** グローバル配列の要素を直接解放すると、無効なメモリアドレスが発生する可能性があります。

**getenv** と **_putenv_s** は、グローバル変数 **_environ** を使用して環境テーブルにアクセスします。 **_wgetenv** と **_wputenv_s** **_wenviron** を使用します。 **_putenv_s** と **_wputenv_s** によって **_environ** および **_wenviron** の値が変更される可能性があります。これにより、 **main** の *envp* 引数と **wmain** への **_wenvp** 引数が無効になります。 そのため、 **_environ** または **_wenviron** を使用して環境情報にアクセスする方が安全です。 **_Putenv_s** と **_wputenv_s** とグローバル変数との関係の詳細については、「 [_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」を参照してください。

> [!NOTE]
> 関数の **_putenv_s** および **_getenv_s** ファミリは、スレッドセーフではありません。 **_getenv_s** が文字列を変更して **_putenv_s** いるときに文字列ポインターを返すことがあり、その結果、ランダムにエラーが発生する可能性があります。 これらの関数の呼び出しが同期されていることを確認する必要があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_putenv_s**|\<stdlib.h>|
|**_wputenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

**_Putenv_s** の使用方法を示すサンプルについては、「 [getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv、 _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv、_wsearchenv](searchenv-wsearchenv.md)<br/>
