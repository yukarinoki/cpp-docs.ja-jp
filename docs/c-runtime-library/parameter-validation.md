---
title: パラメーターの検証
description: Microsoft C ランタイムライブラリのパラメーター検証の説明。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- parameters, validation
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
ms.openlocfilehash: 8378e4bf9bdfc950002c3ed8c3ef50c27a3c162d
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765258"
---
# <a name="parameter-validation"></a>パラメーターの検証

セキュリティが強化された CRT 関数のほとんどは、 **NULL**のポインターのチェック、整数が有効な範囲内にある、または列挙値が有効であることなど、パラメーターを検証します。 無効なパラメーターが見つかった場合は、無効なパラメーターハンドラーが呼び出されます。

## <a name="invalid-parameter-handler-routine"></a>無効なパラメーター ハンドラー ルーチン

C ランタイムライブラリ関数は、無効なパラメーターを検出すると、エラーに関する情報をキャプチャしてから、無効なパラメーターハンドラーディスパッチ関数をラップするマクロを呼び出します。 [_Invalid_parameter](../c-runtime-library/reference/invalid-parameter-functions.md)、 [_invalid_parameter_noinfo](../c-runtime-library/reference/invalid-parameter-functions.md)、 [_invalid_parameter_noinfo_noreturn](../c-runtime-library/reference/invalid-parameter-functions.md)のいずれかになります。 どのディスパッチ関数が呼び出されるかは、コードがそれぞれ、デバッグビルド、リテールビルド、またはエラーが回復可能と見なされないかどうかによって異なります。

デバッグビルドでは、通常、無効なパラメーターマクロによって、ディスパッチ関数が呼び出される前に失敗したアサーションとデバッガーのブレークポイントが生成されます。 このコードを実行すると、アサーションは、オペレーティングシステムとランタイムライブラリのバージョンに応じて、"Abort"、"Retry"、および "Continue" などの選択肢を持つダイアログボックスでユーザーに報告される場合があります。 これらのオプションを使用すると、ユーザーはすぐにプログラムを終了したり、デバッガーをアタッチしたり、既存のコードを実行してディスパッチ関数を呼び出すことができます。

無効なパラメーターハンドラーディスパッチ関数は、現在割り当てられている無効なパラメーターハンドラーを呼び出します。 既定では、無効なパラメーターはを呼び出します `_invoke_watson` 。これにより、アプリケーションがミニダンプを閉じて生成します。 オペレーティングシステムで有効になっている場合、分析のためにクラッシュダンプを Microsoft に送信するかどうかを確認するダイアログボックスが表示されます。

この動作を変更するには、関数 [_set_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) または [_set_thread_local_invalid_parameter_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) を使用して、無効なパラメーターハンドラーを独自の関数に設定します。 指定した関数がアプリケーションを終了しない場合、無効なパラメーターを取得した関数に制御が返されます。 CRT では、通常、これらの関数は関数の実行を停止し、 `errno` エラーコードに設定して、エラーコードを返します。 多くの場合、 `errno` 値と戻り値は両方とも、 `EINVAL` 無効なパラメーターを示します。 場合によっては、より具体的なエラー コードが返されます。たとえば、無効なファイル ポインターがパラメーターとして渡された場合の `EBADF` などです。

`errno` の詳細については、[errno、_doserrno、_sys_errlist, and _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) をご覧ください。

## <a name="see-also"></a>関連項目

[CRT のセキュリティ機能](../c-runtime-library/security-features-in-the-crt.md)\
[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
