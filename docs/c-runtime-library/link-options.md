---
title: リンク オプション
ms.date: 11/04/2016
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- legacy_stdio_float_rounding.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
ms.openlocfilehash: ea71faab639a8c0a09d6e332618dd7e09159a4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351109"
---
# <a name="link-options"></a>リンク オプション

CRT lib ディレクトリには、コード変更を加えずに特定の CRT 機能を有効にする複数のオブジェクト ファイルが含まれます。 これらは、リンカー コマンド ラインに追加するだけで使用することができるため、「リンク オプション」と呼ばれます。

これらのオブジェクトの CLR ピュア モード バージョンは、Visual Studio 2015 で非推奨となり、Visual Studio 2017 ではサポートされていません。 ネイティブおよび /clr コードに標準のバージョンを使用してください。

|ネイティブおよび /clr|ピュア モード|説明|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|既定のファイルの変換モードをバイナリに設定します。 [_fmode](../c-runtime-library/fmode.md) をご覧ください。|
|chkstk.obj|該当なし|CRT を使用していない場合にスタック チェックと alloca サポートを提供します。|
|commode.obj|pcommode.obj|グローバル コミット フラグを "コミット" に設定します。 [fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md) および [fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) をご覧ください。|
|exe_initialize_mta.lib|該当なし|EXE のセットアップ中に MTA アパートメントが初期化され、グローバルなスマート ポインターで COM オブジェクトが使用できるようになります。 このオプションではシャットダウン中に MTA アパートメントの参照がリークされるため、DLL では使用しないでください。 このリンクは、combase.h を含め、_EXE_INITIALIZE_MTA を定義する場合と同等です。 |
|fp10.obj|該当なし|既定の精度制御を 64 ビットに変更します。 「[浮動小数点サポート](../c-runtime-library/floating-point-support.md)」をご覧ください。|
|invalidcontinue.obj|pinvalidcontinue.obj|何もしない既定の無効なパラメーター ハンドラーを設定します。つまり、CRT 関数に渡される無効なパラメーターによってエラー番号が設定され、エラーの結果が返されます。|
|legacy_stdio_float_rounding.obj|該当なし|Windows 10 19041 ユニバーサル C ランタイムで浮動小数点値 ([たとえば printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)を使用する場合) の印刷が修正されました。 これで、表現可能な浮動小数点数を正確に丸め[、fesetenv](../c-runtime-library/reference/fesetenv1.md)によって要求された浮動小数点丸めが考慮されるようになりました。 この動作の更新プログラムは、Visual Studio 2019 バージョン 16.2 以降で使用できます。 従来の動作は、以前のバージョンの Visual Studio で使用されるか、このリンク オプションを提供することによって使用されます。|
|loosefpmath.obj|該当なし|浮動小数点コードが非正規化値を許容するようにします。|
|newmode.obj|pnewmode.obj|失敗時に [malloc](../c-runtime-library/reference/malloc.md) が新しいハンドラーを呼び出すようにします。 [_set_new_mode](../c-runtime-library/reference/set-new-mode.md)、[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)、[calloc](../c-runtime-library/reference/calloc.md)、[realloc](../c-runtime-library/reference/realloc.md) をご覧ください。|
|noarg.obj|pnoarg.obj|argc および argv のすべてのプロセスを無効にします。|
|nochkclr.obj|該当なし|何も行いません。 プロジェクトから削除してください。|
|noenv.obj|pnoenv.obj|CRT のキャッシュ済み環境の作成を無効にします。|
|nothrownew.obj|pnothrownew.obj|CRT で new のスローしないバージョンを有効にします。 「[new および delete 演算子](../cpp/new-and-delete-operators.md)」をご覧ください。|
|setargv.obj|psetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|
|threadlocale.obj|pthreadlocale.obj|既定ですべての新しいスレッドに対してスレッド単位のロケールを有効にします。|
|wsetargv.obj|pwsetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|

## <a name="see-also"></a>関連項目

- [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
