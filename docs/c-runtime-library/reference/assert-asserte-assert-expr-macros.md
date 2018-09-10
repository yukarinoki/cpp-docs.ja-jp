---
title: _ASSERT、_ASSERTE、_ASSERT_EXPR マクロ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
- _ASSERTE
- ASSERTE
- _ASSERT
- _ASSERT_EXPR
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _ASSERTE macro
- macros, debugging with
- debug reporting macros
- _ASSERT macro
- _ASSERT_EXPR macro
ms.assetid: e98fd2a6-7f5e-4aa8-8fe8-e93490deba36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 254550acf94acb846826bc0efe76ef26753c54b8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107591"
---
# <a name="assert-asserte-assertexpr-macros"></a>_ASSERT、_ASSERTE、_ASSERT_EXPR マクロ

式を評価し、結果がデバッグ レポートを生成**False** (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
// Typical usage:
_ASSERT_EXPR( booleanExpression, message );
_ASSERT( booleanExpression );
_ASSERTE( booleanExpression );
```

### <a name="parameters"></a>パラメーター

*ブール式*<br/>
0 以外 (true) または 0 (false) に評価されるスカラー式 (ポインター式)。

*message*<br/>
レポートの一部として表示するワイド文字列。

## <a name="remarks"></a>Remarks

**_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**マクロ、デバッグ中に前提条件をチェックするためのクリーンでシンプルなメカニズムをアプリケーションに提供します。 アプリケーションの製品版ビルドで呼び出されないようにするために `#ifdef` ステートメントで囲む必要がないため、これらのマクロには高い柔軟性があります。 この柔軟性は、 [_DEBUG](../../c-runtime-library/debug.md) マクロを使用することで実現されます。 **_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**変更するにはのみ **_DEBUG**はコンパイル時に定義します。 ときに **_DEBUG**が定義されていない場合、これらのマクロの呼び出しはプリプロセス時に削除されます。

**_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**評価、*ブール式*引数とすると、結果は**false**(0)、出力メッセージを診断し呼び出し[_CrtDbgReportW](crtdbgreport-crtdbgreportw.md)デバッグ レポートを生成します。 **_ASSERT**マクロは、単純な診断メッセージを出力します **_ASSERTE**メッセージで失敗した式の文字列表現が含まれていますと **_ASSERT_EXPR**含まれています、*メッセージ*診断メッセージ内の文字列。 これらのマクロは何もしない場合に*ブール式*0 以外の値に評価されます。

**_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**呼び出す **_CrtDbgReportW**、これにより、すべての出力がワイド文字。 **_ASSERTE**の Unicode 文字を正しく印刷*ブール式*と **_ASSERT_EXPR**の Unicode 文字を出力します*メッセージ*します。

**_ASSERTE**マクロが失敗した式を指定および **_ASSERT_EXPR**により生成されたレポートでのメッセージを指定するを参照しなくても、問題を識別するためにユーザーを有効にする、アプリケーションのソース コード。 ただし、欠点をすべて*メッセージ*によって出力される **_ASSERT_EXPR**とすべての式によって評価 **_ASSERTE**出力 (デバッグ バージョン) に含まれる文字列定数として、アプリケーションのファイルです。 そのため、多くの場合は呼び出しが **_ASSERT_EXPR**または **_ASSERTE**、これらの式が、出力ファイルのサイズを大幅に増加します。

[_CrtSetReportMode](crtsetreportmode.md) や [_CrtSetReportFile](crtsetreportfile.md) 関数で明示的に指定しない限り、以下と等しい設定を持つメッセージがポップアップ ダイアログ ボックスに表示されます。

```C
_CrtSetReportMode(CRT_ASSERT, _CRTDBG_MODE_WNDW);
````

**_CrtDbgReportW**デバッグ レポートを生成し、宛先または現在のレポート モードまたはモードと定義されているファイルに基づいて、変換先を決定します、 **_CRT_ASSERT**レポートの種類。 既定では、アサーション エラーとエラーは、デバッグ メッセージ ウィンドウに送られます。 [_CrtSetReportMode](crtsetreportmode.md) 関数と [_CrtSetReportFile](crtsetreportfile.md) 関数は、各レポートの種類の宛先を定義するために使用されます。

クリックしたときに、変換先は、デバッグ メッセージ ウィンドウで、ユーザー、**再試行**ボタン、 **_CrtDbgReportW** 1 を返しますの原因、 **_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**マクロを・ イン タイム (JIT) デバッグが有効なデバッガーを開始します。

レポート処理の詳細については、 [_CrtDbgReport、_CrtDbgReportW](crtdbgreport-crtdbgreportw.md) 関数を参照してください。 アサーション失敗を解決し、これらのマクロをデバッグ エラーの処理機構として使用する方法の詳細については、「 [確認とレポートのためのマクロの使用](/visualstudio/debugger/macros-for-reporting)」を参照してください。

加え、 **_ASSERT** 、マクロ、[アサート](assert-macro-assert-wassert.md)マクロはプログラム ロジックの検証に使用できます。 このマクロは、ライブラリのデバッグ バージョンとリリース バージョンの両方で使用できます。 [_RPT、_RPTF](rpt-rptf-rptw-rptfw-macros.md) デバッグ マクロをデバッグ レポート生成のために使用することもできますが、式の評価は行いません。 **_RPT**マクロは、簡単なレポートを生成します。 **_RPTF**マクロは、生成されたレポートがレポート マクロが呼び出されたソース ファイルと行番号を含めます。 これらのマクロのワイド文字バージョンを利用できます (**_RPTW**、 **_RPTFW**)。 ワイド文字バージョンは、ワイド文字列がすべての文字列パラメーターと出力で使用できるという点を除き、ナロー文字バージョンと同一です。

**_ASSERT_EXPR**、 **_ASSERT**と **_ASSERTE**マクロを含めることによって利用され\<crtdbg.h >、アプリケーションは、デバッグとリンクする必要がありますC ランタイム ライブラリのバージョンと **_DEBUG**が定義されているは、これらのマクロは、その他のランタイム関数を呼び出すためです。

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-----------|---------------------|
|**_ASSERT_EXPR**、 **_ASSERT**、 **_ASSERTE**|\<crtdbg.h>|

## <a name="example"></a>例

このプログラムで呼び出しが、 **_ASSERT**と **_ASSERTE**条件をテストするマクロ`string1 == string2`します。 条件が失敗した場合、これらのマクロは診断メッセージを出力します。 **_RPT**と **_RPTF**マクロのグループの代替手段としてこのプログラムで実行がも、 **printf**関数。

```C
// crt_ASSERT_macro.c
// compile with: /D_DEBUG /MTd /Od /Zi /link /verbose:lib /debug
//
// This program uses the _ASSERT and _ASSERTE debugging macros.
//

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

int main()
{
   char *p1, *p2;

   // The Reporting Mode and File must be specified
   // before generating a debug report via an assert
   // or report macro.
   // This program sends all report types to STDOUT.
   _CrtSetReportMode(_CRT_WARN, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_WARN, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ERROR, _CRTDBG_FILE_STDOUT);
   _CrtSetReportMode(_CRT_ASSERT, _CRTDBG_MODE_FILE);
   _CrtSetReportFile(_CRT_ASSERT, _CRTDBG_FILE_STDOUT);

   // Allocate and assign the pointer variables.
   p1 = (char *)malloc(10);
   strcpy_s(p1, 10, "I am p1");
   p2 = (char *)malloc(10);
   strcpy_s(p2, 10, "I am p2");

   // Use the report macros as a debugging
   // warning mechanism, similar to printf.
   // Use the assert macros to check if the
   // p1 and p2 variables are equivalent.
   // If the expression fails, _ASSERTE will
   // include a string representation of the
   // failed expression in the report.
   // _ASSERT does not include the
   // expression in the generated report.
   _RPT0(_CRT_WARN,
       "Use the assert macros to evaluate the expression p1 == p2.\n");
   _RPTF2(_CRT_WARN, "\n Will _ASSERT find '%s' == '%s' ?\n", p1, p2);
   _ASSERT(p1 == p2);

   _RPTF2(_CRT_WARN, "\n\n Will _ASSERTE find '%s' == '%s' ?\n",
          p1, p2);
   _ASSERTE(p1 == p2);

   _RPT2(_CRT_ERROR, "'%s' != '%s'\n", p1, p2);

   free(p2);
   free(p1);

   return 0;
}
```

```Output
Use the assert macros to evaluate the expression p1 == p2.
crt_ASSERT_macro.c(54) :
Will _ASSERT find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(55) : Assertion failed!
crt_ASSERT_macro.c(58) :

Will _ASSERTE find 'I am p1' == 'I am p2' ?
crt_ASSERT_macro.c(59) : Assertion failed: p1 == p2
'I am p1' != 'I am p2'
```

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[assert マクロ、_assert、_wassert](assert-macro-assert-wassert.md)<br/>
[_RPT、_RPTF、_RPTW、_RPTFW Macros](rpt-rptf-rptw-rptfw-macros.md)<br/>
