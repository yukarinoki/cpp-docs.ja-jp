---
title: 演算子&gt;= (deque) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::operator>=
dev_langs:
- C++
helpviewer_keywords:
- operator>= member [STL/CLR]
ms.assetid: 14746073-60a3-4088-b7ea-f987e963d418
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 98e7e13bcf25c5332751ac56cf83ffe36d962ad2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138871"
---
# <a name="operatorgt-deque-stlclr"></a>演算子&gt;= (deque) (STL/CLR)
Deque より大きいか等しい比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value>  
    bool operator>=(deque<Value>% left,  
        deque<Value>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(left` `<` `right)`です。 テストするために使用するかどうか`left`する前に順序付けされていない`right`がいつ行われる 2 つの deque の要素で要素を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_deque_operator_ge.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::deque<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] >= [a b c] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] >= [a b c] is True  
[a b c] >= [a b d] is False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [演算子 = = (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)   
 [deque::operator! = (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)   
 [演算子\<(deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)   
 [operator > (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)   
 [operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)