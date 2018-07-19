---
title: 制御の移動 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8bec66d25be2cb56c75f42f60af2ccd5e3f759ad
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943898"
---
# <a name="transfers-of-control"></a>制御の移動
使用することができます、 **goto**ステートメントまたは**ケース**でラベル付け、**切り替える**初期化子を越えて分岐するプログラムを指定するステートメント。 初期化子を含む宣言がジャンプ ステートメントの発生元のブロックで囲まれたブロックに存在しない限り、このようなコードは無効です。  
  
 次の例は、オブジェクト `total`、`ch`、`i` を宣言して初期化するループを示します。 ありますが、不適切なも**goto**初期化子を越えて制御を転送するステートメント。  
  
```cpp 
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 上記の例では、 **goto**ステートメントの初期化を越えて制御を転送しようとする`i`します。 ただし、`i` が宣言されていても初期化されていない場合、転送は有効になります。  
  
 オブジェクト`total`と`ch`として機能するブロックで宣言された、*ステートメント*の**中**ステートメントを使用して、そのブロックが終了したときに破棄されます、 **break**ステートメント。  
  
