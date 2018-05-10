---
title: 数値演算エラー M6201 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a15e841cfc8daf1abdafc9997698807e7356af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6201"></a>数値演算エラー M6201
'function': _DOMAIN エラー  
  
 指定された関数の引数は、その関数の有効な入力値のドメイン外でした。  
  
## <a name="example"></a>例  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 このエラーが、`_matherr`関数名、その引数、およびエラーの種類を持つ関数です。 書き直すことができます、`_matherr`特定の浮動小数点演算の実行時エラーの処理をカスタマイズする関数。