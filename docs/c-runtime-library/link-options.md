---
title: リンク オプション | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91b97c653a5f035a767fbedcfcbfdfa7ca178327
ms.sourcegitcommit: 038f1406b1172318f8832371ad14176f788c44fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50132154"
---
# <a name="link-options"></a>リンク オプション

CRT lib ディレクトリには、コード変更を加えずに特定の CRT 機能を有効にする複数のオブジェクト ファイルが含まれます。 これらは、リンカー コマンド ラインに追加するだけで使用することができるため、「リンク オプション」と呼ばれます。

これらのオブジェクトの CLR ピュア モード バージョンは、Visual Studio 2015 で非推奨となり、Visual Studio 2017 ではサポートされていません。 ネイティブおよび /clr コードに標準のバージョンを使用してください。

|ネイティブおよび /clr|ピュア モード|説明|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|既定のファイルの変換モードをバイナリに設定します。 [_fmode](../c-runtime-library/fmode.md) をご覧ください。|
|chkstk.obj|N/A|CRT を使用していない場合にスタック チェックと alloca サポートを提供します。|
|commode.obj|pcommode.obj|グローバル コミット フラグを "コミット" に設定します。 [fopen、_wfopen](../c-runtime-library/reference/fopen-wfopen.md) および [fopen_s、_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) をご覧ください。|
|exe_initialize_mta.lib|N/A|EXE のセットアップ中に MTA アパートメントが初期化され、グローバルなスマート ポインターで COM オブジェクトが使用できるようになります。 このオプションではシャットダウン中に MTA アパートメントの参照がリークされるため、DLL では使用しないでください。 このリンクは、combase.h を含め、_EXE_INITIALIZE_MTA を定義する場合と同等です。 |
|fp10.obj|N/A|既定の精度制御を 64 ビットに変更します。 「[浮動小数点サポート](../c-runtime-library/floating-point-support.md)」をご覧ください。|
|invalidcontinue.obj|pinvalidcontinue.obj|何もしない既定の無効なパラメーター ハンドラーを設定します。つまり、CRT 関数に渡される無効なパラメーターによってエラー番号が設定され、エラーの結果が返されます。|
|loosefpmath.obj|N/A|浮動小数点コードが非正規化値を許容するようにします。|
|newmode.obj|pnewmode.obj|失敗時に [malloc](../c-runtime-library/reference/malloc.md) が新しいハンドラーを呼び出すようにします。 [_set_new_mode](../c-runtime-library/reference/set-new-mode.md)、[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)、[calloc](../c-runtime-library/reference/calloc.md)、[realloc](../c-runtime-library/reference/realloc.md) をご覧ください。|
|noarg.obj|pnoarg.obj|argc および argv のすべてのプロセスを無効にします。|
|nochkclr.obj|N/A|処理を行いません。 プロジェクトから削除してください。|
|noenv.obj|pnoenv.obj|CRT のキャッシュ済み環境の作成を無効にします。|
|nothrownew.obj|pnothrownew.obj|CRT で new のスローしないバージョンを有効にします。 「[new および delete 演算子](../cpp/new-and-delete-operators.md)」をご覧ください。|
|setargv.obj|psetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|
|threadlocale.obj|pthreadlocale.obj|既定ですべての新しいスレッドに対してスレッド単位のロケールを有効にします。|
|wsetargv.obj|pwsetargv.obj|コマンド ライン引数のワイルドカードの展開を有効にします。 「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」をご覧ください。|

## <a name="see-also"></a>関連項目

- [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
