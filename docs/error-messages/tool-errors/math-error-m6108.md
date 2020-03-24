---
title: 数値演算エラー M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 68e6ae823613d87eb01c443b564b46746259cd7b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173726"
---
# <a name="math-error-m6108"></a>数値演算エラー M6108

平方根

平方根演算のオペランドが負の値でした。

プログラムは終了コード136で終了します。

> [!NOTE]
>  C ランタイムライブラリの `sqrt` 関数および FORTRAN の組み込み関数**SQRT**では、このエラーは生成されません。 C `sqrt` 関数は、演算を実行する前に引数をチェックし、オペランドが負の場合はエラー値を返します。 FORTRAN **SQRT**関数は、このエラーの代わりにドメインエラー [M6201](../../error-messages/tool-errors/math-error-m6201.md)を生成します。
