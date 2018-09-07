---
title: デバッグ ルーチン | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- c.debug
dev_langs:
- C++
helpviewer_keywords:
- debugging [CRT], using macros
- macros, debugging with
- debug routines
- debug macros
- debugging [CRT], runtime routines
ms.assetid: cb4d2664-10f3-42f7-a516-595558075471
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46018d2ec8747b1fac459e1ac1d28b59eea2385b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203473"
---
# <a name="debug-routines"></a>デバッグ ルーチン

C ランタイム ライブラリのデバッグ バージョンには、プログラムのデバッグを容易にする多くの診断サービスが用意されており、開発者は次のことが可能になります。

- デバッグ中にランタイム関数に直接ステップ インする

- アサーション、エラー、および例外を解決する

- ヒープ割り当てを追跡し、メモリ リークを防ぐ

- ユーザーにデバッグ メッセージを報告する

## <a name="debug-versions-of-the-c-runtime-library-routines"></a>C ランタイム ライブラリ ルーチンのデバッグ バージョン

これらのルーチンを使うには、[_DEBUG](../c-runtime-library/debug.md) フラグを定義する必要があります。 これらのルーチンはすべて、アプリケーションの製品版ビルドでは何も行いません。 新しいデバッグ ルーチンの使い方について詳しくは、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」をご覧ください。

|ルーチンによって返される値|用途|
|-------------|---------|
|[_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|式を評価し、結果が FALSE の場合はデバッグ レポートを生成します|
|[_ASSERTE](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|**_ASSERT** に似ていますが、生成されるレポートに失敗した式が含まれます|
|[_CrtCheckMemory](../c-runtime-library/reference/crtcheckmemory.md)|デバッグ ヒープに割り当てられたメモリ ブロックの整合性を確認します|
|[_CrtDbgBreak](../c-runtime-library/reference/crtdbgbreak.md)|ブレークポイントを設定します。|
|[_CrtDbgReport、_CrtDbgReportW](../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)|ユーザー メッセージのあるデバッグ レポートを生成し、3 つの宛先にレポートを送信します|
|[_CrtDoForAllClientObjects](../c-runtime-library/reference/crtdoforallclientobjects.md)|ヒープ内のすべての **_CLIENT_BLOCK** 型に対して、アプリケーションによって提供される関数を呼び出します|
|[_CrtDumpMemoryLeaks](../c-runtime-library/reference/crtdumpmemoryleaks.md)|重大なメモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします|
|[_CrtIsMemoryBlock](../c-runtime-library/reference/crtismemoryblock.md)|指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子が設定されていることを確認します|
|[_CrtIsValidHeapPointer](../c-runtime-library/reference/crtisvalidheappointer.md)|指定したポインターがローカル ヒープ内にあることを検証します|
|[_CrtIsValidPointer](../c-runtime-library/reference/crtisvalidpointer.md)|指定したメモリ範囲で読み取りおよび書き込みが可能であることを確認します|
|[_CrtMemCheckpoint](../c-runtime-library/reference/crtmemcheckpoint.md)|デバッグ ヒープの現在の状態を取得し、アプリケーションが指定した **_CrtMemState** 構造体に格納します|
|[_CrtMemDifference](../c-runtime-library/reference/crtmemdifference.md)|2 つのメモリ状態の大幅な違いを比較し、結果を返します|
|[_CrtMemDumpAllObjectsSince](../c-runtime-library/reference/crtmemdumpallobjectssince.md)|指定されたチェックポイントの取得以降、またはプログラムの実行開始以降の、ヒープ上のオブジェクトに関する情報をダンプします|
|[_CrtMemDumpStatistics](../c-runtime-library/reference/crtmemdumpstatistics.md)|指定されたメモリ状態のデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします|
|[_CrtReportBlockType](../c-runtime-library/reference/crtreportblocktype.md)|特定のデバッグ ヒープ ブロック ポインターに関連付けられたブロックの型および細分化された型を返します。|
|[_CrtSetAllocHook](../c-runtime-library/reference/crtsetallochook.md)|C ランタイム デバッグ メモリ割り当てプロセスにフックして、クライアント定義割り当て関数をインストールします|
|[_CrtSetBreakAlloc](../c-runtime-library/reference/crtsetbreakalloc.md)|指定されたオブジェクト割り当て順序番号にブレークポイントを設定します|
|[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md)|**_crtDbgFlag** フラグの状態を取得または変更して、デバッグ ヒープ マネージャーの割り当て動作を制御します|
|[_CrtSetDumpClient](../c-runtime-library/reference/crtsetdumpclient.md)|**_CLIENT_BLOCK** 型のメモリ ブロックをダンプするためにデバッグ ダンプ関数が呼び出されるたびに呼び出されるアプリケーション定義関数をインストールします|
|[_CrtSetReportFile](../c-runtime-library/reference/crtsetreportfile.md)|**_CrtDbgReport** による特定の種類のレポートの出力先として使用されるファイルまたはストリームを特定します|
|[_CrtSetReportHook](../c-runtime-library/reference/crtsetreporthook.md)|C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールします|
|[_CrtSetReportHook2、_CrtSetReportHookW2](../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)|C ランタイム デバッグ レポート プロセスにフックして、クライアント定義レポート関数をインストールまたはアンインストールします。|
|[_CrtSetReportMode](../c-runtime-library/reference/crtsetreportmode.md)|**_CrtDbgReport** によって生成される特定の種類のレポートの一般的な出力先を指定します|
|[_RPT&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|書式指定文字列と可変数の引数と共に **_CrtDbgReport** を呼び出してデバッグ レポートを生成することによって、アプリケーションの進行状況を追跡します。 ソース ファイルと行番号の情報は提供されません。|
|[_RPTF&#91;0,1,2,3,4&#93;](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md)|**_RPTn** マクロに似ていますが、レポート要求の発生元となったソース ファイル名と行番号を提供します|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ、指定された数のメモリ ブロックをヒープに割り当てます|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|ブロックの拡張や縮小によって、ヒープ内の指定されたメモリのブロックをサイズ変更します|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|ヒープ上のメモリのブロックを解放します|
|[_fullpath_dbg、_wfullpath_dbg](../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md)|指定された相対パス名の絶対または完全パス名を作成します。メモリを割り当てるために、[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) が使われます。|[System::IO::File::Create](https://msdn.microsoft.com/library/system.io.file.create.aspx)|
|[_getcwd_dbg、_wgetcwd_dbg](../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md)|現在の作業ディレクトリを取得します。メモリを割り当てるために、[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) が使われます。|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ、メモリ ブロックをヒープに割り当てます|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|ヒープ内のメモリ ブロックのサイズを計算します|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|ブロックの移動やサイズ変更によって、ヒープ内の指定されたメモリのブロックを再割り当てします|
|[_strdup_dbg、_wcsdup_dbg](../c-runtime-library/reference/strdup-dbg-wcsdup-dbg.md)|文字列を複製します。メモリを割り当てるために、[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) が使われます。|
|[_tempnam_dbg、_wtempnam_dbg](../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md)|一時ファイルを作成するために使用できる名前を生成します。メモリを割り当てるために、[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md) が使われます。|

## <a name="c-runtime-routines-that-are-not-available-in-source-code-form"></a>ソース コードの形式で使用できない C ランタイム ルーチン

デバッガーを使用して、デバッグ プロセス中にほとんどの C ランタイム ルーチンのソース コードをステップ実行することができます。 ただし、一部のテクノロジは Microsoft によって所有物と見なされるため、これらのルーチンのサブセットにソース コードが提供されません。 これらのルーチンのほとんどは例外処理または浮動小数点処理のグループに属していますが、他のグループに属しているものもあります。 次の表は、これらのルーチンの一覧です。

||||
|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[acosh](../c-runtime-library/reference/acosh-acoshf-acoshl.md)|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|
|[asinh](../c-runtime-library/reference/asinh-asinhf-asinhl.md)|[atan、atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[atanh](../c-runtime-library/reference/atanh-atanhf-atanhl.md)|
|[ベッセル関数](../c-runtime-library/reference/bessel-functions-j0-j1-jn-y0-y1-yn.md)|[_cabs](../c-runtime-library/reference/cabs.md)|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|
|[_chgsign](../c-runtime-library/reference/chgsign-chgsignf-chgsignl.md)|[_clear87、_clearfp](../c-runtime-library/reference/clear87-clearfp.md)|[_control87、_controlfp](../c-runtime-library/reference/control87-controlfp-control87-2.md)|
|[copysign](../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)|[cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|
|[Exp](../c-runtime-library/reference/exp-expf.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[_finite](../c-runtime-library/reference/finite-finitef.md)|
|[floor](../c-runtime-library/reference/floor-floorf-floorl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[_fpclass](../c-runtime-library/reference/fpclass-fpclassf.md)|
|[_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)|[_fpreset](../c-runtime-library/reference/fpreset.md)|[frexp](../c-runtime-library/reference/frexp.md)|
|[_hypot](../c-runtime-library/reference/hypot-hypotf-hypotl-hypot-hypotf-hypotl.md)|[_isnan](../c-runtime-library/reference/isnan-isnan-isnanf.md)|[ldexp](../c-runtime-library/reference/ldexp.md)|
|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[_logb](../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|
|[longjmp](../c-runtime-library/reference/longjmp.md)|[_matherr](../c-runtime-library/reference/matherr.md)|[modf](../c-runtime-library/reference/modf-modff-modfl.md)|
|[_nextafter](../c-runtime-library/reference/nextafter-functions.md)|[pow](../c-runtime-library/reference/pow-powf-powl.md)|[printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|
|[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_scalb](../c-runtime-library/reference/scalb.md)|[scanf_s](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|
|[scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[setjmp](../c-runtime-library/reference/setjmp.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|
|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|[_status87、_statusfp](../c-runtime-library/reference/status87-statusfp-statusfp2.md)|
|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)||

**printf** および **scanf** ルーチンの大部分でソース コードを使用できますが、ソース コードが提供されない他のルーチンへの内部呼び出しが行われています。

## <a name="routines-that-behave-differently-in-a-debug-build-of-an-application"></a>アプリケーションのデバッグ ビルドでは動作が異なるルーチン

一部の C ランタイム関数と C++ 演算子は、アプリケーションのデバッグ ビルドから呼び出されたときの動作が異なります。 アプリケーションのデバッグ ビルドは、`_DEBUG` フラグを定義するか、C ランタイム ライブラリのデバッグ バージョンとリンクすることによって作成できます。動作上の違いは、通常、デバッグ プロセスをサポートするために、機能が追加されたりルーチンによって情報が提供されたりすることです。 次の表は、これらのルーチンの一覧です。

|||
|-|-|
|C の [abort](../c-runtime-library/reference/abort.md) ルーチン|C++ の [delete](../cpp/delete-operator-cpp.md) 演算子|
|C の [assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) ルーチン|C++ の [new](../cpp/new-operator-cpp.md) 演算子|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
[ランタイム エラー チェック](../c-runtime-library/run-time-error-checking.md)<br/>
