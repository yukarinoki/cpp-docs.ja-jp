---
title: 式ステートメント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d94acdfff2fdea2cc35d0856940270ba82e131af
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405257"
---
# <a name="expression-statement"></a>式ステートメント
式ステートメントを使用すると、式が評価されます。 式ステートメントの結果として、制御が移動したり、イテレーションが発生したりすることはありません。  
  
 式ステートメントの構文は、次のように、単純です。  
  
## <a name="syntax"></a>構文  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Remarks  
 式ステートメント内の式はすべて評価され、次のステートメントが実行される前にすべての副作用が完了します。 最も一般的に使用される式ステートメントは、代入と関数呼び出しです。  セミコロンだけと呼ばれる空の式ステートメントと見なされます、式は省略可能であるため、 [null](../cpp/null-statement.md)ステートメント。  
  
## <a name="see-also"></a>関連項目  
 [C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)