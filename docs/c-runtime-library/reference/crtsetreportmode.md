---
title: _CrtSetReportMode | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetReportMode
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
- _CrtSetReportMode
- CrtSetReportMode
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.assetid: 3ecc6a12-afdd-4242-b046-8187ff6d4b36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd4ac54cd4bd8877e8a6ba32f585ef5d5e29e65c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="crtsetreportmode"></a>_CrtSetReportMode

によって生成される特定のレポートの種類の宛先の指定 **_CrtDbgReport**とそのマクロを呼び出す[_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)など[_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](assert-asserte-assert-expr-macros.md)、 [_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ](assert-asserte-assert-expr-macros.md)、 [_RPT、_RPTF、_RPTW、_RPTFW のマクロ](rpt-rptf-rptw-rptfw-macros.md)、および[_RPT、_RPTF、_RPTW、_RPTFW のマクロ](rpt-rptf-rptw-rptfw-macros.md)(デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>パラメーター

*reportType*<br/>
レポートの種類:**前述**、 **_CRT_ERROR**、および **_CRT_ASSERT**です。

*された*<br/>
新しいレポート モード*reportType*です。

## <a name="return-value"></a>戻り値

正常に終了、 **_CrtSetReportMode**で指定されたレポートの種類では、以前のレポート モードまたはモードを返します*reportType*です。 無効な値として渡される場合*reportType*か、または無効なモードは指定*された*、 **_CrtSetReportMode**として無効なパラメーター ハンドラーが呼び出されます説明されている[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、-1 を返します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_CrtSetReportMode**出力先を指定する **_CrtDbgReport**です。 マクロ[_ASSERT](assert-asserte-assert-expr-macros.md)、 [_ASSERTE](assert-asserte-assert-expr-macros.md)、 [_RPT](rpt-rptf-rptw-rptfw-macros.md)、および[_RPTF](rpt-rptf-rptw-rptfw-macros.md)呼び出す **_CrtDbgReport**、 **_CrtSetReportMode**これらのマクロで指定したテキストの出力先を指定します。

ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtSetReportMode**プリプロセス時に削除されます。

呼び出さない場合 **_CrtSetReportMode**メッセージの出力先を定義するのにし、次の既定値は有効にします。

- アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。

- Windows アプリケーションからの警告は、デバッガーの出力ウィンドウに送られます。

- コンソール アプリケーションからの警告は表示されません。

次の表は、Crtdbg.h で定義されているレポートの種類の一覧です。

|レポートの種類|説明|
|-----------------|-----------------|
|**前述**|早急の対応を必要としない警告、メッセージ、および情報。|
|**_CRT_ERROR**|エラー、回復不能な問題、および早急の対応を必要とする問題。|
|**_CRT_ASSERT**|アサーションの失敗 (に評価される式をアサート**FALSE**)。|

**_CrtSetReportMode**関数で指定された新しいレポート モードを割り当てます*された*で指定されたレポートの種類に*reportType*し、以前に定義されたを返しますレポート モード*reportType*です。 次の表で使用できる選択肢*された*と結果の動作 **_CrtDbgReport**です。 これらのオプションは、Crtdbg.h でビット フラグとして定義されています。

|レポート モード|_CrtDbgReport の動作|
|-----------------|-----------------------------|
|**_CRTDBG_MODE_DEBUG**|デバッガーの出力ウィンドウにメッセージを書き込みます。|
|**_CRTDBG_MODE_FILE**|ユーザーが指定したファイル ハンドルにメッセージを書き込みます。 書き込み先として使用する特定のファイルまたはストリームを定義するには、[_CrtSetReportFile](crtsetreportfile.md) を呼び出す必要があります。|
|**_CRTDBG_MODE_WNDW**|と共にメッセージを表示するメッセージ ボックスを作成、[中止](abort.md)、**再試行**、および**無視**ボタン。|
|**_CRTDBG_REPORT_MODE**|返します*された*、指定された*reportType*:<br /><br /> 1 **_CRTDBG_MODE_FILE**<br /><br /> 2 **_CRTDBG_MODE_DEBUG**<br /><br /> 4 **_CRTDBG_MODE_WNDW**|

各レポートの種類は、1 つ、2 つ、または 3 つのモードか、モードなしを使用して報告できます。 したがって、1 つのレポートの種類に対して複数の書き込み先を定義することができます。 たとえば、次のコード フラグメントは、アサーションの失敗にされ、デバッグ メッセージ ウィンドウに送信されるを**stderr**:

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

さらに、各レポートの種類のレポート モードは、個別に制御できます。 たとえば、ことを指定することは、 *reportType*の**前述**するときに出力デバッグ文字列に送信される、 **_CRT_ASSERT**するデバッグ メッセージ ウィンドウを使用して表示されます送信される**stderr**に説明したようです。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_CrtSetReportMode**|\<crtdbg.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
