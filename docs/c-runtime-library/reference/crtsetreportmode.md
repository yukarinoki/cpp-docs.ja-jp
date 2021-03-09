---
title: _CrtSetReportMode
description: '詳細については、次を参照してください: _CrtSetReportMode'
ms.date: 3/8/2021
api_name:
- _CrtSetReportMode
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CrtSetReportMode
- CrtSetReportMode
helpviewer_keywords:
- _CrtSetReportMode function
- CrtSetReportMode function
ms.openlocfilehash: 770ef955894563dc11dee9f13946067d5d024c11
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514383"
---
# `_CrtSetReportMode`

**_CrtDbgReport** によって生成される特定のレポートの種類の出力先、および [`_CrtDbgReport, _CrtDbgReportW`](crtdbgreport-crtdbgreportw.md) [ `_ASSERT, _ASSERTE, _ASSERT_EXPR` マクロ](assert-asserte-assert-expr-macros.md)、 [ `_ASSERT, _ASSERTE, _ASSERT_EXPR` マクロ](assert-asserte-assert-expr-macros.md)、 [ `_RPT, _RPTF, _RPTW, _RPTFW` マクロ](rpt-rptf-rptw-rptfw-macros.md)、 [ `_RPT, _RPTF, _RPTW, _RPTFW` マクロ](rpt-rptf-rptw-rptfw-macros.md)などを呼び出すマクロ (デバッグバージョンのみ) を指定します。

## <a name="syntax"></a>構文

```C
int _CrtSetReportMode(
   int reportType,
   int reportMode
);
```

### <a name="parameters"></a>パラメーター

*`reportType`*\
レポートの種類: **`_CRT_WARN`** 、 **`_CRT_ERROR`** 、および **`_CRT_ASSERT`** 。

*`reportMode`*\
の新しいレポートモードまたはモード *`reportType`* 。

## <a name="return-value"></a>戻り値

正常に完了し **`_CrtSetReportMode`** た場合、は、で指定されたレポートの種類に対して以前のレポートモードを返し *`reportType`* ます。 無効な値がとして渡された場合 *`reportType`* 、または無効なモードがに指定されている場合は *`reportMode`* 、「 **`_CrtSetReportMode`** [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **`errno`** をに設定 **`EINVAL`** し、-1 を返します。 詳細については、[`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を参照してください。

## <a name="remarks"></a>注釈

**`_CrtSetReportMode`** の出力先を指定し **`_CrtDbgReport`** ます。 マクロ、、、およびは、マクロで [`_ASSERT`](assert-asserte-assert-expr-macros.md) [`_ASSERTE`](assert-asserte-assert-expr-macros.md) [`_RPT`](rpt-rptf-rptw-rptfw-macros.md) [`_RPTF`](rpt-rptf-rptw-rptfw-macros.md) **`_CrtDbgReport`** **`_CrtSetReportMode`** 指定されたテキストの出力先を指定します。

が定義されて [`_DEBUG`](../../c-runtime-library/debug.md) いない場合、の呼び出し **`_CrtSetReportMode`** はプリプロセス中に削除されます。

**`_CrtSetReportMode`** メッセージの出力先を定義するためにを呼び出さないと、次の既定値が有効になります。

- アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。

- Windows アプリケーションからの警告は、デバッガーの出力ウィンドウに送られます。

- コンソール アプリケーションからの警告は表示されません。

次の表に、で定義されているレポートの種類の一覧を示し `Crtdbg.h` ます。

|レポートの種類|説明|
|-----------------|-----------------|
|**`_CRT_WARN`**|早急の対応を必要としない警告、メッセージ、および情報。|
|**`_CRT_ERROR`**|エラー、回復不能な問題、および早急の対応を必要とする問題。|
|**`_CRT_ASSERT`**|アサーションエラー (に評価されるアサート式 **`FALSE`** )。|

関数は、で指定された **`_CrtSetReportMode`** 新しいレポートモード *`reportMode`* をで指定されたレポートの種類に割り当て、 *`reportType`* 以前に定義したのレポートモードを返し *`reportType`* ます。 次の表に、で使用できる選択肢 *`reportMode`* と、結果として得られるの動作を示し **`_CrtDbgReport`** ます。 これらのオプションは、Crtdbg.h でビット フラグとして定義されています。

|レポート モード|_CrtDbgReport の動作|
|-----------------|-----------------------------|
|**`_CRTDBG_MODE_DEBUG`**|デバッガーの出力ウィンドウにメッセージを書き込みます。|
|**`_CRTDBG_MODE_FILE`**|ユーザーが指定したファイル ハンドルにメッセージを書き込みます。 [`_CrtSetReportFile`](crtsetreportfile.md) は、送信先として使用する特定のファイルまたはストリームを定義するために呼び出される必要があります。|
|**`_CRTDBG_MODE_WNDW`**|[`abort`](abort.md)、 **`Retry`** 、および **無視** ボタンと共にメッセージを表示するメッセージボックスを作成します。|
|**`_CRTDBG_REPORT_MODE`**|*`reportMode`* 指定されたのを返し *`reportType`* ます。<br /><br /> 1   **`_CRTDBG_MODE_FILE`**<br /><br /> 3   **`_CRTDBG_MODE_DEBUG`**<br /><br /> 4/4   **`_CRTDBG_MODE_WNDW`**|

各レポートの種類は、1 つ、2 つ、または 3 つのモードか、モードなしを使用して報告できます。 したがって、1 つのレポートの種類に対して複数の書き込み先を定義することができます。 たとえば、次のコードフラグメントでは、アサーションエラーがデバッグメッセージウィンドウとの両方に送信され **`stderr`** ます。

```C
_CrtSetReportMode( _CRT_ASSERT, _CRTDBG_MODE_FILE | _CRTDBG_MODE_WNDW );
_CrtSetReportFile( _CRT_ASSERT, _CRTDBG_FILE_STDERR );
```

さらに、各レポートの種類のレポート モードは、個別に制御できます。 たとえば、のを出力デバッグ文字列に送信するように指定し、前に説明 *`reportType`* **`_CRT_WARN`** した **`_CRT_ASSERT`** ようにデバッグメッセージウィンドウを使用して表示し、に送信することができ **`stderr`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**`_CrtSetReportMode`**|`<crtdbg.h>`|`<errno.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

**ライブラリ:**[C ランタイムライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグバージョンのみ。

## <a name="see-also"></a>こちらもご覧ください

[デバッグルーチン](../../c-runtime-library/debug-routines.md)
