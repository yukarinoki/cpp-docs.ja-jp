---
description: 詳細については、「エラー処理 (CRT)」を参照してください。
title: エラー処理 (CRT)
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, C routines for
- logic errors
- error handling, library routines
- testing, for program errors
ms.assetid: 125ac697-9eb0-4152-a440-b7842f23d97f
ms.openlocfilehash: 4aa81f1152fe991398b38f6b433993aecb8be401
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331142"
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
