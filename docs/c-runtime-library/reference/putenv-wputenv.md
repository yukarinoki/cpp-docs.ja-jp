---
title: _putenv、_wputenv
ms.date: 4/2/2020
api_name:
- _putenv
- _wputenv
- _o__putenv
- _o__wputenv
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
ms.openlocfilehash: 3e74959e6c6cdb2e27ce0d68ba40d02d64949904
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333040"
---
# <a name="_putenv-_wputenv"></a>_putenv、_wputenv

環境変数を作成、変更、または削除します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md)」をご覧ください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>パラメーター

*羨望文字列*<br/>
環境文字列定義。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返し、エラーの場合は -1 を返します。

## <a name="remarks"></a>解説

**_putenv**関数は、新しい環境変数を追加するか、既存の環境変数の値を変更します。 環境変数は、プロセス (たとえば、プログラムにリンクされるライブラリの既定の検索パス) が実行される環境を定義します。 **_wputenv**はワイド文字の **_putenv**です。**_wputenv**の*envstring*引数はワイド文字列です。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*envstring*引数は *、varname*= *value_string* *value_string*の形式の文字列へのポインタ*varname*である必要があります。 *varname*がすでに環境の一部である場合、その値は*value_string*に置き換えられます。それ以外の場合は、新しい*varname*変数とその*value_string*値が環境に追加されます。 変数を環境から削除*するには、* value_stringを空にするか *、varname*= だけを指定します。

**_putenv**と **_wputenv**は、現在のプロセスに対してローカルな環境にのみ影響します。コマンド・レベル環境の変更には使用できません。 つまり、これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体だけを対象とし、プロセス用にオペレーティング システムで作成された環境 "セグメント" は参照しません。 現在のプロセスが終了すると、環境は、呼び出し元プロセス (ほとんどの場合、オペレーティング システムのレベル) のレベルに戻ります。 ただし、変更された環境**は、** **_exec**または **_wputenv** **_putenv** **システム**、 _spawn によって作成された新しいプロセスに渡すことができます。

環境エントリーを直接変更しないでください **_wputenv** **_putenv。** 特に **、_environ[]** グローバル配列の要素を直接解放すると、無効なメモリがアドレス指定される可能性があります。

**getenv**と **_putenvは**、グローバル変数 **_environ**を使用して環境テーブルにアクセスします。**_wgetenv**と **_wputenv****は _wenviron**を使用します。 **_putenv**と **_wputenv**は **_environ**と **_wenviron**の値を変更する可能性があるため **、_envp**引数は**main**に **、_wenvp**引数は**wmain**に無効になります。 したがって、環境情報にアクセスするには **、_environ**または **_wenviron**を使用する方が安全です。 **_putenv**とグローバル変数と**の_wputenv**の関係の詳細については、「 [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md)」を参照してください。

> [!NOTE]
> **関数の_putenv**と **_getenv**ファミリはスレッド セーフではありません。 **_getenv**文字列を変更しているときに文字列ポインタ**を返_putenv、** ランダムなエラーを引き起こす可能性があります。 これらの関数の呼び出しが同期されていることを確認する必要があります。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

**_putenv**使用方法の例については、 [getenv, _wgetenv](getenv-wgetenv.md)を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv、 _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv、_wsearchenv](searchenv-wsearchenv.md)<br/>
