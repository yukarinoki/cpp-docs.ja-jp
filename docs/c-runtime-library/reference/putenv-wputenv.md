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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a86b58b868c96b6f77af8bfa32036d1a56b2a7cf
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82918868"
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

*envstring*<br/>
環境文字列定義。

## <a name="return-value"></a>戻り値

成功した場合は0を返し、エラーの場合は-1 を返します。

## <a name="remarks"></a>解説

**_Putenv**関数は、新しい環境変数を追加するか、既存の環境変数の値を変更します。 環境変数は、プロセス (たとえば、プログラムにリンクされるライブラリの既定の検索パス) が実行される環境を定義します。 **_wputenv**は **_putenv**のワイド文字バージョンです。**_wputenv**の*envstring*引数は、ワイド文字列です。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

*Envstring*引数は、 *varname*=*value_string*形式の文字列へのポインターである必要があります。 *varname*は、追加または変更する環境変数の名前で、 *value_string*変数の値です。 *Varname*が既に環境の一部である場合、その値は*value_string*; に置き換えられます。それ以外の場合は、新しい*varname*変数とその*value_string*値が環境に追加されます。 空の*value_string*を指定するか、または*varname*= のみを指定することにより、環境から変数を削除できます。

**_putenv**と **_wputenv**は、現在のプロセスに対してローカルな環境にのみ影響します。これらのコマンドを使用して、コマンドレベルの環境を変更することはできません。 つまり、これらの関数は、ランタイム ライブラリからアクセスできるデータ構造体だけを対象とし、プロセス用にオペレーティング システムで作成された環境 "セグメント" は参照しません。 現在のプロセスが終了すると、環境は、呼び出し元プロセス (ほとんどの場合、オペレーティング システムのレベル) のレベルに戻ります。 ただし、変更された環境は **_spawn**、 **_exec**、または**システム**によって作成された新しいプロセスに渡すことができ、これらの新しいプロセスは **_putenv**および **_wputenv**によって追加された新しい項目を取得します。

環境エントリを直接変更しないでください。代わりに、 **_putenv**または **_wputenv**を使用して変更してください。 特に、 **_environ []** グローバル配列の要素を直接解放すると、無効なメモリアドレスにつながる可能性があります。

**getenv**と **_putenv**は、グローバル変数 **_environ**を使用して環境テーブルにアクセスします。**_wgetenv**と **_wputenv** **_wenviron**を使用します。 **_putenv**と **_wputenv**によって **_environ**および **_wenviron**の値が変更される可能性があるため、 **main**への **_envp**引数と**wmain**への **_wenvp**引数が無効になります。 そのため、 **_environ**または **_wenviron**を使用して環境情報にアクセスする方が安全です。 **_Putenv**とグローバル変数への **_wputenv**の関係の詳細については、「 [_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」を参照してください。

> [!NOTE]
> 関数の **_putenv**および **_getenv**ファミリは、スレッドセーフではありません。 **_getenv**が文字列を変更しているときに文字列ポインターを返すことで、ランダム **_putenv**にエラーが発生する可能性があります。 これらの関数の呼び出しが同期されていることを確認する必要があります。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

**_Putenv**の使用方法の例については、「 [getenv、_wgetenv](getenv-wgetenv.md)」を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv、 _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv、_wsearchenv](searchenv-wsearchenv.md)<br/>
