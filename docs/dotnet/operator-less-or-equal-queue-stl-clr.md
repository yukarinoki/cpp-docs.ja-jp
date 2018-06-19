---
title: 演算子&lt;= (キュー) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::queue::operator<=
dev_langs:
- C++
helpviewer_keywords:
- operator<= member [STL/CLR]
ms.assetid: 63b7f908-4f6b-40d6-bcc6-22970760789d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1ffdf411d60c9ebdb404899f1f7048174b9be2c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136380"
---
# <a name="operatorlt-queue-stlclr"></a>演算子&lt;= (キュー) (STL/CLR)
以下のキューの比較できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    bool operator<=(queue<Value, Container>% left,  
        queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(right < left)`です。 テストするために使用するかどうか`left`後に順序付けされていない`right`要素によって比較対象の要素が 2 つのキューの場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_queue_operator_le.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] <= [a b c] is {0}",   
        c1 <= c1);   
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",   
        c2 <= c1);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] <= [a b c] is True  
[a b d] <= [a b c] is False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [キュー (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [演算子 = = (キュー) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)   
 [operator! = (キュー) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)   
 [演算子\<(キュー) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)   
 [operator > = (キュー) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)   
 [operator> (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)