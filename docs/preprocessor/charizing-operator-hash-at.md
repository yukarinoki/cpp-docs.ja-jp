---
title: 演算子文字定数化 (#@) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6aa18936497f0415da331697aceb26f26345500
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42545786"
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)
**Microsoft 固有の仕様**  
  
文字定数化演算子は、マクロの引数でのみ使用できます。 場合`#@`仮パラメーターの前に、実引数の単一引用符で囲まれているし、マクロが展開されている場合は、文字として扱わマクロの定義でします。 例えば:  
  
```  
#define makechar(x)  #@x  
```  
  
は、次のステートメント  
  
```  
a = makechar(b);  
```  
  
を次のように展開します  
  
```  
a = 'b';  
```  
  
単一引用符文字は charizing 演算子では使用できません。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 
[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)