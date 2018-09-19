---
title: 数値演算エラー M6108 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1624a89b472733b4adb5563c8ba52e0b03dcaa2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048618"
---
# <a name="math-error-m6108"></a>数値演算エラー M6108

平方根

平方根演算のオペランドが負の値。

終了コード 136 でプログラムを終了します。

> [!NOTE]
>  `sqrt` C ランタイム ライブラリと FORTRAN の組み込み関数の関数**SQRT**このエラーは生成されません。 C`sqrt`関数は、操作を実行する前に、引数をチェックし、オペランドが負の場合は、エラー値を返します。 FORTRAN **SQRT**関数には、ドメイン エラーが生成されます。 [M6201](../../error-messages/tool-errors/math-error-m6201.md)このエラーの代わりにします。