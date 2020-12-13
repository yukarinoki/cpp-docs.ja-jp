---
description: 詳細については、「Math Error M6108」を参照してください。
title: 数値演算エラー M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: 1a0acf13bd166e499334cb13de33093c2c804f5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143885"
---
# <a name="math-error-m6108"></a>数値演算エラー M6108

平方根

平方根演算のオペランドが負の値でした。

プログラムは終了コード136で終了します。

> [!NOTE]
> `sqrt`C ランタイムライブラリの関数と FORTRAN の組み込み関数 **SQRT** では、このエラーは生成されません。 C 関数は、 `sqrt` 演算を実行する前に引数をチェックし、オペランドが負の場合はエラー値を返します。 FORTRAN **SQRT** 関数は、このエラーの代わりにドメインエラー [M6201](../../error-messages/tool-errors/math-error-m6201.md) を生成します。
