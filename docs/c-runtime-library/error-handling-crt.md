---
title: エラー処理 (CRT)
ms.date: 11/04/2016
f1_keywords:
- c.errors
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: 7b3a5676c9297b1d7805f92b3a15cc71518ecd65
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551218"
---
# <a name="error-handling-crt"></a>エラー処理 (CRT)

これらのルーチンを使用し、プログラム エラーを処理します。

## <a name="error-handling-routines"></a>エラー処理ルーチン

|ルーチンによって返される値|使用|
|-------------|---------|
|[assert](../c-runtime-library/reference/assert-macro-assert-wassert.md) マクロ|プログラミング論理エラーのテストであり、ランタイム ライブラリのリリース バージョンとデバッグ バージョンの両方で利用できます。|
|[_ASSERT マクロ、_ASSERTE マクロ](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)|**assert** に似ていますが、ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|
|[clearerr](../c-runtime-library/reference/clearerr.md)|エラー インジケーターをリセットします。 **rewind** を呼び出すか、ストリームを閉じると、エラー インジケーターもリセットされます。|
|[_eof](../c-runtime-library/reference/eof.md)|下位入出力のファイルの終わりを確認します。|
|[feof](../c-runtime-library/reference/feof.md)|ファイルの終わりをテストします。 ファイルの終わりは、**_read** が 0 を返したときにも指示されます。|
|[ferror](../c-runtime-library/reference/ferror.md)|ストリーム入出力エラーをテストします。|
|[_RPT マクロ、_RPTF](../c-runtime-library/reference/rpt-rptf-rptw-rptfw-macros.md) マクロ|**printf** に似たレポートを生成しますが、ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|
|[_set_error_mode](../c-runtime-library/reference/set-error-mode.md)|プログラムを終了させる可能性があるエラーに対して C ランタイムがエラー メッセージを書き込む、既定以外の位置を **__error_mode** を変更して決定します。|
|[_set_purecall_handler](../c-runtime-library/reference/get-purecall-handler-set-purecall-handler.md)|純粋仮想関数呼び出しのハンドラーを設定します。|

## <a name="see-also"></a>関連項目

- [カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)
