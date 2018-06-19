---
title: 繰り返しステートメント (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1973223d6aab44d4c5d8652111d3e6b8251676fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418914"
---
# <a name="iteration-statements-c"></a>繰り返しステートメント (C++)
繰り返しステートメントにより、ループ終了条件に応じて、ステートメント (または複合ステートメント) が複数回実行されます。 これらのステートメントが複合ステートメントの場合は、場合を除き、順序どおりに実行されますか、 [break](../cpp/break-statement-cpp.md)ステートメントまたは[続行](../cpp/continue-statement-cpp.md)ステートメントが見つかりました。  
  
 C には、次の 4 つの繰り返しステートメントが用意されています:[中に](../cpp/while-statement-cpp.md)、[は](../cpp/do-while-statement-cpp.md)、[の](../cpp/for-statement-cpp.md)、および[範囲ベースの for](../cpp/range-based-for-statement-cpp.md)です。 ゼロ (false) に、終了式が評価されるまで、またはループの終了時に強制されるまでこれらの各反復処理、 **break**ステートメントです。 次の表は、これらのステートメントと操作をまとめたものです。それぞれについては以降のセクションで詳しく説明します。  
  
### <a name="iteration-statements"></a>繰り返しステートメント  
  
|ステートメント|評価のタイミング|初期化|インクリメント|  
|---------------|------------------|--------------------|---------------|  
|`while`|ループの先頭|×|×|  
|**do**|ループの最後|×|×|  
|**for**|ループの先頭|[はい]|[はい]|  
|**範囲ベースの for**|ループの先頭|[はい]|[はい]|  
  
 繰り返しステートメントのステートメント部分は宣言にできません。 ただし、宣言を含む複合ステートメントにすることができます。  
  
## <a name="see-also"></a>関連項目  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)