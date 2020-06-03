---
title: コンソール入出力とポート入出力
ms.date: 11/04/2016
helpviewer_keywords:
- routines, console and port I/O
- routines
- ports, I/O routines
- I/O [CRT], console
- I/O [CRT], port
- I/O routines, console and port I/O
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
ms.openlocfilehash: 5b4dc2a081ea11bd84d932f55b5b247de81f296a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79443450"
---
# <a name="console-and-port-io"></a>コンソール入出力とポート入出力

これらのルーチンは、コンソールまたは指定したポートで読み取りと書き込みを行います。 コンソール入出力は、ストリーム入出力や低レベルの入出力ライブラリ ルーチンとは互換性がありません。 入出力を実行する前にコンソールやポートを開くまたは閉じる必要はないため、このカテゴリには開くまたは閉じるルーチンはありません。 Windows オペレーティング システムでは、これらの関数からの出力は常にコンソールに送られ、リダイレクトできません。

## <a name="console-and-port-io-routines"></a>コンソール入出力ルーチンとポート入出力ルーチン

|ルーチン|用途|
|-------------|---------|
|[_cgets、_cgetws](../c-runtime-library/cgets-cgetws.md)、[_cgets_s、_cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|コンソールから文字列を読み取る|
|[_cprintf、_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)、[_cprintf_s、_cprintf_s_l、_cwprintf_s、_cwprintf_s_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|コンソールに書式付きデータを書き込む|
|[_cputs](../c-runtime-library/reference/cputs-cputws.md)|コンソールに文字列を書き込む|
|[_cscanf、_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)、[_cscanf_s、_cscanf_s_l、_cwscanf_s、_cwscanf_s_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|コンソールから書式付きデータを読み取る|
|[_getch、_getwch](../c-runtime-library/reference/getch-getwch.md)|コンソールから文字を読み取る|
|[_getche、_getwche](../c-runtime-library/reference/getch-getwch.md)|コンソールから文字を読み取り、エコーする|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|指定した I/O ポートから 1 バイトを読み取る|
|[_inpd](../c-runtime-library/inp-inpw-inpd.md)|指定した I/O ポートからダブル ワードを読み取る|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|指定した I/O ポートから 2 バイト ワードを読み取る|
|[_kbhit](../c-runtime-library/reference/kbhit.md)|コンソールのキーボード操作をチェックし、コンソールからの読み取りを試みる前に使用する|
|[_outp](../c-runtime-library/outp-outpw-outpd.md)|指定した I/O ポートに 1 バイトを書き込む|
|[_outpd](../c-runtime-library/outp-outpw-outpd.md)|指定した I/O ポートにダブル ワードを書き込む|
|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|指定した I/O ポートにワードを書き込む|
|[_putch、_putwch](../c-runtime-library/reference/putch-putwch.md)|コンソールに文字を書き込む|
|[_ungetch、_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|コンソールから読み取った最後の文字を "戻す" ことで次の読み取り文字にする|

## <a name="see-also"></a>参照

[入出力](../c-runtime-library/input-and-output.md)<br/>
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
