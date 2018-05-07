---
title: 数値演算エラー M6108 |Microsoft ドキュメント
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
ms.openlocfilehash: 4dfeca48aa04ebfbc097649e5c25253166c50dad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6108"></a>数値演算エラー M6108
平方根算出  
  
 平方根演算のオペランドが負の値。  
  
 プログラムは、終了コード 136 で終了します。  
  
> [!NOTE]
>  `sqrt` C ランタイム ライブラリおよび FORTRAN 組み込み関数で関数**SQRT**このエラーは生成されません。 C`sqrt`関数は、操作を実行する前に、引数をチェックし、オペランドが負の場合は、エラー値を返します。 FORTRAN **SQRT**関数には、ドメイン エラーが生成されます。 [M6201](../../error-messages/tool-errors/math-error-m6201.md)このエラーの代わりにします。