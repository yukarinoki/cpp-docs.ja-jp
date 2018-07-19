---
title: _RPT、_RPTF、_RPTW、_RPTFW のマクロ | Microsoft Docs
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
- RPT3
- RPTF4
- _RPT4
- RPT1
- _RPTF0
- RPTF3
- _RPTF4
- RPTF1
- RPT4
- _RPT1
- _RPT0
- RPT0
- _RPTF2
- RPTF0
- _RPT3
- _RPT2
- _RPTF3
- RPT2
- _RPTF1
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- _RPTW3 macro
- _RPT0 macro
- RPTW4 macro
- _RPTF3 macro
- _RPTW4 macro
- RPTF4 macro
- RPTFW2 macro
- RPTW macros
- RPT1 macro
- _RPTF macros
- RPTFW3 macro
- _RPTW0 macro
- _RPTF0 macro
- macros, debugging with
- _RPTW2 macro
- RPTF3 macro
- RPT3 macro
- RPT0 macro
- _RPT macros
- RPTW3 macro
- _RPTFW macros
- debug reporting macros
- RPTF macros
- RPT macros
- _RPTW macros
- RPTF2 macro
- _RPTF1 macro
- _RPT1 macro
- _RPT4 macro
- _RPTFW2 macro
- _RPTFW1 macro
- RPTF0 macro
- _RPT2 macro
- RPTFW macros
- _RPTW1 macro
- _RPTFW0 macro
- RPT4 macro
- _RPT3 macro
- _RPTFW3 macro
- _RPTF4 macro
- _RPTFW4 macro
- _RPTF2 macro
- RPTW0 macro
- RPTFW4 macro
- RPTFW0 macro
- RPTW2 macro
- RPTF1 macro
- RPT2 macro
- RPTFW1 macro
- RPTW1 macro
ms.assetid: a5bf8b30-57f7-4971-8030-e773b7a1ae13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a53a069138b4e54988be008917e5ca2b24fa0a6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411885"
---
# <a name="rpt-rptf-rptw-rptfw-macros"></a>_RPT、_RPTF、_RPTW、_RPTFW のマクロ

デバッグ レポートを生成してアプリケーションの進行状況を追跡します (デバッグ バージョンのみ)。 なお*n*内の引数の数を指定*args* 0、1、2、3、4、または 5 を指定できます。

## <a name="syntax"></a>構文

```C
_RPT
      n
      (
   reportType,
   format,
...[args]
);
_RPTFn(
   reportType,
   format,
   [args]
);
_RPTWn(
   reportType,
   format
   [args]
);
_RPTFWn(
   reportType,
   format
   [args]
);
```

### <a name="parameters"></a>パラメーター

*reportType*レポートの種類:**前述**、 **_CRT_ERROR**、または **_CRT_ASSERT**です。

*形式*ユーザー メッセージの作成に使用するコントロールの書式設定文字列。

*args*で使用される代替引数*形式*です。

## <a name="remarks"></a>コメント

すべてのマクロ、 *reportType*と*形式*パラメーター。 また、マクロ名に追加された数字で示される最大 4 つの追加引数を受け取る場合もあります。 たとえば、 **_RPT0**と **_RPTF0**追加の引数を受け取らない **_RPT1**と **_RPTF1**かかる*arg1*、 **_RPT2**と **_RPTF2**かかる*arg1*と**arg2**のようにします。

**_RPT**と **_RPTF**マクロと似ています、 [printf](printf-printf-l-wprintf-wprintf-l.md)デバッグ プロセス中にアプリケーションの進行状況を追跡するために使用されることがあるために機能します。 ただし、これらのマクロはより柔軟な**printf**で囲む必要がないため **#ifdef**れないようにするステートメントは、アプリケーションの製品版ビルドでと呼ばれます。 この柔軟性を使用して、 [_DEBUG](../../c-runtime-library/debug.md)マクロ以外の場合は、 **_RPT**と **_RPTF**のマクロはのみ使用可能な場合に、 **_DEBUG**フラグは、定義されています。 ときに **_DEBUG**が定義されていない、これらのマクロの呼び出しはプリプロセス時に削除されます。

**_RPTW**と **_RPTFW**マクロは、これらのマクロのワイド文字バージョンです。 ようなもの**wprintf**を引数としてワイド文字列を実行します。

**_RPT**マクロの呼び出し、 [_CrtDbgReport](crtdbgreport-crtdbgreportw.md)ユーザー メッセージを含むデバッグ レポートを生成する関数。 **_RPTW**マクロの呼び出し、 **_CrtDbgReportW**ワイド文字と同じレポートを生成する関数。 **_RPTF**と **_RPTFW**マクロは、ここで、レポート マクロが呼び出された、さらに、ユーザー メッセージをソース ファイルと行番号を持つデバッグ レポートを作成します。 置き換えることによって、ユーザー メッセージの作成、 **arg**[*n*] 引数を*形式*文字列、によって定義されている同じ規則を使用して、 [printf](printf-printf-l-wprintf-wprintf-l.md)関数。

**_CrtDbgReport**または **_CrtDbgReportW**デバッグ レポートを生成し、その現在のレポート モードに基づいて変換先およびに対して定義されているファイルを決定*reportType*です。 [_CrtSetReportMode](crtsetreportmode.md) 関数と [_CrtSetReportFile](crtsetreportfile.md) 関数は、各レポートの種類の宛先を定義するために使用されます。

場合、 **_RPT**マクロが呼び出されると、どちらも **_CrtSetReportMode**も **_CrtSetReportFile**されました呼び出されると、メッセージは次のように表示します。

|レポートの種類|出力先|
|-----------------|------------------------|
|**前述**|警告テキストは表示されません。|
|**_CRT_ERROR**|ポップアップ ウィンドウ。 `_CrtSetReportMode(_CRT_ERROR, _CRTDBG_MODE_WNDW);` が指定されている場合と同じです。|
|**_CRT_ASSERT**|同じ **_CRT_ERROR**です。|

宛先がデバッグ メッセージ ウィンドウと、ユーザーが選択した場合、**再試行**ボタン、 **_CrtDbgReport**または **_CrtDbgReportW**原因でこれらのマクロを開始する、1 を返します、デバッガー、ジャスト イン タイム (JIT) デバッグが有効になっています。 これらのマクロをデバッグ エラーの処理機構として使用する方法の詳細については、[確認とレポート用マクロの使用](/visualstudio/debugger/macros-for-reporting)に関するページを参照してください。

デバッグ レポートを生成するマクロが他にも 2 つ存在します。 [_ASSERT](assert-asserte-assert-expr-macros.md) マクロは、その式の引数が FALSE に評価される場合にのみ、レポートを生成します。 [_ASSERTE](assert-asserte-assert-expr-macros.md)は同様 **_ASSERT**、生成されたレポートで失敗した式が含まれています。

## <a name="requirements"></a>要件

|マクロ|必須ヘッダー|
|-----------|---------------------|
|**_RPT**マクロ|\<crtdbg.h>|
|**_RPTF**マクロ|\<crtdbg.h>|
|**_RPTW**マクロ|\<crtdbg.h>|
|**_RPTFW**マクロ|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

これらはマクロであり、Crtdbg.h を組み込むと取得されますが、アプリケーションは、デバッグ ライブラリのいずれかとリンクする必要があります。これらのマクロは、他のランタイム関数を呼び出すからです。

## <a name="example"></a>例

「[_ASSERT](assert-asserte-assert-expr-macros.md)」のトピックの例を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
