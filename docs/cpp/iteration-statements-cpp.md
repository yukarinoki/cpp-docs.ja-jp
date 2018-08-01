---
title: 繰り返しステートメント (C++) |Microsoft Docs
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
ms.openlocfilehash: 988d46b3f4b2e20ff14227fda70a6f39ac95756c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402898"
---
# <a name="iteration-statements-c"></a>繰り返しステートメント (C++)
繰り返しステートメントにより、ループ終了条件に応じて、ステートメント (または複合ステートメント) が複数回実行されます。 これらのステートメントが複合ステートメントの場合は、場合を除き、順序どおりに実行されますか、 [break](../cpp/break-statement-cpp.md)ステートメントまたは[続行](../cpp/continue-statement-cpp.md)ステートメントが見つかりました。  
  
 C には、次の 4 つの繰り返しステートメントが用意されています:[中](../cpp/while-statement-cpp.md)、[は](../cpp/do-while-statement-cpp.md)、[の](../cpp/for-statement-cpp.md)と[範囲ベースの for](../cpp/range-based-for-statement-cpp.md)します。 0 (false) に、終了式が評価されるまで、またはが強制的にループを終了するまでこれらの各反復処理を**break**ステートメント。 次の表は、これらのステートメントと操作をまとめたものです。それぞれについては以降のセクションで詳しく説明します。  
  
### <a name="iteration-statements"></a>繰り返しステートメント  
  
|ステートメント|評価のタイミング|初期化|インクリメント|  
|---------------|------------------|--------------------|---------------|  
|**while**|ループの先頭|いいえ|いいえ|  
|**do**|ループの最後|いいえ|いいえ|  
|**for**|ループの先頭|[はい]|[はい]|  
|**範囲ベースの for**|ループの先頭|[はい]|[はい]|  
  
 繰り返しステートメントのステートメント部分は宣言にできません。 ただし、宣言を含む複合ステートメントにすることができます。  
  
## <a name="see-also"></a>関連項目  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)