---
description: '詳細については、次を参照してください: _CrtDbgReport、_CrtDbgReportW'
title: _CrtDbgReport、_CrtDbgReportW
ms.date: 11/04/2016
api_name:
- _CrtDbgReport
- _CrtDbgReportW
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
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
ms.openlocfilehash: 523dc65f846804b13b83bf08b0499b2459fe22ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319805"
---
# <a name="_crtdbgreport-_crtdbgreportw"></a>_CrtDbgReport、_CrtDbgReportW

デバッグ メッセージのあるレポートを生成し、3 つの宛先 (デバッグ バージョンのみ) にレポートを送信します。

## <a name="syntax"></a>構文

```C
int _CrtDbgReport(
   int reportType,
   const char *filename,
   int linenumber,
   const char *moduleName,
   const char *format [,
   argument] ...
);
int _CrtDbgReportW(
   int reportType,
   const wchar_t *filename,
   int linenumber,
   const wchar_t *moduleName,
   const wchar_t *format [,
   argument] ...
);
```

### <a name="parameters"></a>パラメーター

*reportType*<br/>
レポートの種類: **_CRT_WARN**、 **_CRT_ERROR**、および **_CRT_ASSERT**。

*filename*<br/>
アサート/レポートが発生したソースファイル名へのポインターまたは **NULL**。

*linenumber*<br/>
アサート/レポートが発生したソースファイル内の行番号または **NULL**。

*moduleName*<br/>
アサートまたはレポートが発生したモジュール (.exe または .dll) 名へのポインター。

*format*<br/>
ユーザー メッセージの作成に使用される書式指定文字列へのポインター。

*argument*<br/>
*形式* で使用される省略可能な置換引数。

## <a name="return-value"></a>戻り値

すべてのレポートの出力先では、エラーが発生した場合は-1 を返し、エラーが発生しなかった場合は0を返します。 **_CrtDbgReport** と **_CrtDbgReportW** 。 ただし、レポートの宛先がデバッグ メッセージ ウィンドウで、ユーザーが **[再試行]** をクリックすると、これらの関数は 1 を返します。 ユーザーがデバッグ メッセージ ウィンドウの **[中止]** をクリックすると、関数はすぐに中止され、値は返されません。

[_RPT、_RPTF](rpt-rptf-rptw-rptfw-macros.md)デバッグマクロは **_CrtDbgReport** を呼び出してデバッグレポートを生成します。 これらのマクロのワイド文字バージョンと [_ASSERT、_ASSERTE](assert-asserte-assert-expr-macros.md)、 [_RPTW](rpt-rptf-rptw-rptfw-macros.md) および [_RPTFW](rpt-rptf-rptw-rptfw-macros.md)は、 **_CrtDbgReportW** を使用してデバッグレポートを生成します。 **_CrtDbgReport** または **_CrtDbgReportW** が1を返した場合、just-in-time (JIT) デバッグが有効になっていれば、これらのマクロはデバッガーを開始します。

## <a name="remarks"></a>解説

**_CrtDbgReport** と **_CrtDbgReportW** は、デバッグレポートファイル、デバッグモニター (Visual Studio デバッガー)、またはデバッグメッセージウィンドウの3つの異なる宛先にデバッグレポートを送信できます。 2 つの構成関数 [_CrtSetReportMode](crtsetreportmode.md) および [_CrtSetReportFile](crtsetreportfile.md) は、各レポートの種類の出力先を指定するために使用されます。 これらの関数では、各レポートの種類に対するレポートの宛先を個別に管理できます。 たとえば、 **_CRT_WARN** の *reportType* をデバッグモニターにのみ送信するように指定し、reportType **_CRT_ASSERT** のをデバッグメッセージウィンドウとユーザー定義のレポートファイルに送信することができます。

**_CrtDbgReportW** は **_CrtDbgReport** のワイド文字バージョンです。 すべての出力および文字列のパラメーターは、ワイド文字列内にあり、それ以外の場合は 1 バイト文字バージョンと同じです。

**_CrtDbgReport** および **_CrtDbgReportW** 、 **printf** 関数または **wprintf** 関数で定義されているのと同じ規則を使用して、*引数*[**n**] 引数を *書式指定* 文字列に置き換えることにより、デバッグレポートのユーザーメッセージを作成します。 次にこれらの関数は、 *reportType* に定義されている現在のレポートモードおよびファイルに基づいて、デバッグレポートを生成し、変換先を決定します。 レポートがデバッグメッセージウィンドウに送信されると、 *ファイル名*、 **LineNumber**、および *moduleName* がウィンドウに表示されている情報に含まれます。

次の表に、レポートモード、モード、およびファイルに使用できる選択肢と、 **_CrtDbgReport** と **_CrtDbgReportW** の結果の動作を示します。 これらのオプションは、のビットフラグとして定義されて \<crtdbg.h> います。

|レポート モード|レポート ファイル|**_CrtDbgReport**、 **_CrtDbgReportW** の動作|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|適用できません|Windows [OutputDebugString](/windows/win32/api/debugapi/nf-debugapi-outputdebugstringw) API にメッセージを書き込みます。|
|**_CRTDBG_MODE_WNDW**|適用できません|Windows [MessageBox](/windows/win32/api/winuser/nf-winuser-messagebox) API を呼び出して、メッセージおよび **[中止]**、**[再試行]**、**[無視]** の各ボタンを表示するメッセージ ボックスを作成します。 ユーザーが [ **中止**] をクリックすると、 **_CrtDbgReport** または **_CrtDbgReport** がすぐに中止します。 ユーザーが **[再試行]** をクリックすると、1 を返します。 ユーザーが [ **無視**] をクリックすると、実行が続行され、 **_CrtDbgReport** **_CrtDbgReportW** 0 が返されます。 エラー状況が存在するときに **[無視]** をクリックすると、"未定義の動作" という結果になることがよくあります。|
|**_CRTDBG_MODE_FILE**|**__HFILE**|Windows [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) API を使用して、ユーザーが指定した **ハンドル** にメッセージを書き込みます。ファイルハンドルの有効性は検証されません。アプリケーションは、レポートファイルを開き、有効なファイルハンドルを渡す役割を担います。|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|**Stderr** にメッセージを書き込みます。|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|**Stdout** にメッセージを書き込みます。|

レポートは 1 つ、2 つ、または 3 つの宛先に送信できます。またどの宛先にも送信しないこともできます。 レポート モードおよびレポート ファイルを指定する方法の詳細については、「[_CrtSetReportMode](crtsetreportmode.md)」および「[_CrtSetReportFile](crtsetreportfile.md)」関数を参照してください。 デバッグ マクロおよびレポート関数の使用方法の詳細については、「[レポート用マクロの使用](/visualstudio/debugger/macros-for-reporting)」を参照してください。

アプリケーションが **_CrtDbgReport** と **_CrtDbgReportW** によって提供されるよりも高い柔軟性を必要とする場合は、独自のレポート関数を記述し、 [_CrtSetReportHook](crtsetreporthook.md) 関数を使用して C ランタイムライブラリのレポート機構にフックすることができます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h>|
|**_CrtDbgReportW**|\<crtdbg.h>|

**_CrtDbgReport** と **_CrtDbgReportW** は Microsoft の拡張機能です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

```C
// crt_crtdbgreport.c
#include <crtdbg.h>

int main(int argc, char *argv[]) {
#ifdef _DEBUG
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);
#endif
}
```

レポート関数を変更する方法の例については、「[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)」を参照してください。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
