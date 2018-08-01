---
title: Null ステートメント |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab391bb75dd6e7a2ef1ccf0951fa93770e6cd316
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408777"
---
# <a name="null-statement"></a>Null ステートメント
「Null ステートメント」は、式ステートメントを*式*がありません。 言語の構文でステートメントが必要でも、式の評価が不要な場合に便利です。 1 つのセミコロンで構成されます。  
  
 null ステートメントは、イテレーション ステートメントのプレースホルダーや、複合ステートメントまたは関数の最後でラベルを付けるステートメントとしてよく使用されます。  
  
 次のコードは、ある文字列を別の文字列にコピーする方法を示しており、null ステートメントが組み込まれています。  
  
```cpp 
// null_statement.cpp  
char *myStrCpy( char *Dest, const char *Source )  
{  
    char *DestStart = Dest;  
  
    // Assign value pointed to by Source to  
    // Dest until the end-of-string 0 is  
    // encountered.  
    while( *Dest++ = *Source++ )  
        ;   // Null statement.  
  
    return DestStart;  
}  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [式ステートメント](../cpp/expression-statement.md)