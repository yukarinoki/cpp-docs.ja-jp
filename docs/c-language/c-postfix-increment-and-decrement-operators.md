---
title: C 後置インクリメント演算子と後置デクリメント演算子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f96c48a69f692c8646de5dec8ad8e6431fb63c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381523"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C 後置インクリメント演算子と後置デクリメント演算子
後置インクリメントと後置デクリメントのオペランドは、スカラー型の変更可能な左辺値です。  
  
## <a name="syntax"></a>構文  
 *postfix-expression*:  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 後置インクリメントまたは後置デクリメントの演算結果は、オペランドの値になります。 結果が得られた後で、オペランドの値がインクリメント (またはデクリメント) されます。 次のコードは、後置インクリメント演算子を示しています。  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 この例では、変数 `var` は 0 と比較されてからインクリメントされます。 `var` がインクリメントされる前に正である場合は、次のステートメントが実行されます。 まず、`q` でポイントされるオブジェクトの値が `p` でポイントされるオブジェクトに代入されます。 次に、`q` と `p` がインクリメントされます。  
  
## <a name="see-also"></a>参照  
 [後置インクリメント演算子と後置デクリメント演算子: ++ および --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)