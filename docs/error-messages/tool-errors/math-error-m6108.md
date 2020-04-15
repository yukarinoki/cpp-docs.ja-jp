---
title: 数値演算エラー M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: c6bd403437ee5e55eaf4add288995d0e4aa76c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361972"
---
# <a name="math-error-m6108"></a>数値演算エラー M6108

平方根

平方根演算のオペランドが負の値でした。

プログラムは終了コード 136 で終了します。

> [!NOTE]
> C`sqrt`ランタイム ライブラリの関数と FORTRAN 組み込み関数**SQRT**では、このエラーは生成されません。 C`sqrt`関数は、演算を実行する前に引数をチェックし、オペランドが負の場合はエラー値を返します。 FORTRAN **SQRT**関数は、このエラーではなく、ドメイン エラー [M6201](../../error-messages/tool-errors/math-error-m6201.md)を生成します。
