---
title: マクロ置換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4028ee710cf38b6a4ef929de9a7e4ffad95f3e41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="macro-substitution"></a>マクロでの代入
ときに*マクロ名*が呼び出されるたびに*string1*の定義で文字列が置き換え*string2*です。  
  
## <a name="syntax"></a>構文  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>コメント  
 マクロ置換は大文字小文字を区別、リテラルです。*string1*と*string2*マクロを呼び出すことはできません。 置換では、元の定義は変更されません。 除く任意の定義済みマクロ内のテキストを置き換えることができます[ $$@](../build/filename-macros.md)です。  
  
 スペースまたはタブ前に、コロンです。コロンの後は、リテラルとして解釈されます。 場合*string2*は null、出現するすべての*string1*マクロの定義の文字列から削除されます。  
  
## <a name="see-also"></a>関連項目  
 [NMAKE マクロの使用](../build/using-an-nmake-macro.md)