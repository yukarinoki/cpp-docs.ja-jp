---
title: _CrtSetReportFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportFile
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
- CrtSetReportFile
- _CrtSetReportFile
dev_langs:
- C++
helpviewer_keywords:
- CrtSetReportFile function
- _CrtSetReportFile function
ms.assetid: 3126537e-511b-44af-9c1c-0605265eabc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3df4f54ad8e191dac7110a914bdde1cec888ff9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402339"
---
# <a name="crtsetreportfile"></a>_CrtSetReportFile

使用した後[_CrtSetReportMode](crtsetreportmode.md)を指定する **_CRTDBG_MODE_FILE**メッセージのテキストを受信するファイル ハンドルを指定することができます。 **_CrtSetReportFile**もで使用される[_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)をテキスト (デバッグ バージョンのみ) のコピー先を指定します。

## <a name="syntax"></a>構文

```C
_HFILE _CrtSetReportFile(
   int reportType,
   _HFILE reportFile
);
```

### <a name="parameters"></a>パラメーター

*reportType*<br/>
レポートの種類:**前述**、 **_CRT_ERROR**、および **_CRT_ASSERT**です。

*reportFile*<br/>
に対して新しいレポート ファイル*reportType*です。

## <a name="return-value"></a>戻り値

正常に終了、 **_CrtSetReportFile**で指定されたレポートの種類で定義されている以前のレポート ファイルが返されます*reportType*です。 無効な値が渡された場合*reportType*、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します **_CRTDBG_HFILE_ERROR**です。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_CrtSetReportFile**と共に使用される、 [_CrtSetReportMode](crtsetreportmode.md) 、によって生成される特定のレポートの種類の宛先を定義する関数 **_CrtDbgReport**です。 ときに **_CrtSetReportMode**に割り当てるには呼び出されて、 **_CRTDBG_MODE_FILE**特定のレポートの種類のモードの reporting **_CrtSetReportFile**しを呼び出す必要があります特定のファイルまたはエクスポート先として使用するストリームを定義します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtSetReportFile**プリプロセス時に削除されます。

次の一覧表示で使用できる選択肢*reportFile*と結果の動作 **_CrtDbgReport**です。 これらのオプションは、Crtdbg.h でビット フラグとして定義されています。

- **ファイル ハンドル**

   メッセージの送信先となるファイルのハンドル。 ハンドルの有効性は検証されません。 ファイルのハンドルを開いたり閉じたりする必要があります。 例えば:

   ```C
   HANDLE hLogFile;
   hLogFile = CreateFile("c:\\log.txt", GENERIC_WRITE,
      FILE_SHARE_WRITE, NULL, CREATE_ALWAYS,
      FILE_ATTRIBUTE_NORMAL, NULL);
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, hLogFile);

   _RPT0(_CRT_WARN,"file message\n");
   CloseHandle(hLogFile);
   ```

- **_CRTDBG_FILE_STDERR**

   メッセージを書き込みます**stderr**、次のようにリダイレクトできます。

   ```C
   freopen( "c:\\log2.txt", "w", stderr);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDERR);

   _RPT0(_CRT_ERROR,"1st message\n");
   ```

- **_CRTDBG_FILE_STDOUT**

   メッセージを書き込みます**stdout**、これはリダイレクトできます。

- **_CRTDBG_REPORT_FILE**

   現在のレポート モードを返します。

各レポートの種類によって使用されるレポート ファイルを個別に制御できます。 たとえば、ことを指定することは、 *reportType*の **_CRT_ERROR**に報告する**stderr**中、 *reportType* の **_CRT_ASSERT**ユーザー定義のファイル ハンドルまたはストリームに報告されます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_CrtSetReportFile**|\<crtdbg.h>|\<errno.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
