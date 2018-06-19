---
title: 演算子 = = (スタック) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::stack::operator==
dev_langs:
- C++
helpviewer_keywords:
- operator== member [STL/CLR]
ms.assetid: 862e7130-150a-44ea-9ec4-9f091ab7653d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5dac802bd25b930ac8f03dc599b9e35c6a141955
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135532"
---
# <a name="operator-stack-stlclr"></a>operator== (stack) (STL/CLR)
スタックと同じ比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    bool operator==(stack<Value, Container>% left,  
        stack<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子の関数が、シーケンスがによって制御される場合にのみ true を返します`left`と`right`同じ長さであると、各位置`i`、 `left[i] ==` `right[i]`です。 テストするために使用するかどうか`left`が同じ順序付け`right`要素によって比較対象の要素が 2 つのスタックの場合。  
  
## <a name="example"></a>例  
  
```  
// cliext_stack_operator_eq.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mystack c2;   
    c2.push(L'a');   
    c2.push(L'b');   
    c2.push(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] == [a b c] is {0}",   
        c1 == c1);   
    System::Console::WriteLine("[a b c] == [a b d] is {0}",   
        c1 == c2);   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
 a b d  
[a b c] == [a b c] is True  
[a b c] == [a b d] is False  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [operator! = (スタック) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)   
 [演算子\<(スタック) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)   
 [operator > = (スタック) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)   
 [operator > (スタック) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)   
 [operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)