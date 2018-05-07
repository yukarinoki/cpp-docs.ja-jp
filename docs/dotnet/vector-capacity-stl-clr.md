---
title: vector::capacity (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::capacity
dev_langs:
- C++
helpviewer_keywords:
- capacity member [STL/CLR]
ms.assetid: f82d8da9-8b4d-4288-8d18-8e9ca5911d87
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9a08766c6b23deb4e36ad8c83f9c1f3e2bc1df1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="vectorcapacity-stlclr"></a>vector::capacity (STL/CLR)
コンテナーに割り当てられたストレージのサイズを報告します。  
  
## <a name="syntax"></a>構文  
  
```  
size_type capacity();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスと少なくとも同じ大きさの値を保持するために現在割り当てられている記憶域を返します[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`です。 これを使用するにを被制御シーケンスの記憶域を再割り当てする必要があります、前にどの程度コンテナー サイズを大きくを判断します。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_capacity.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for (int i = 0; i < c1.size(); ++i)   
        System::Console::Write(" {0}", c1.at(i));   
    System::Console::WriteLine();   
  
// increase capacity   
    cliext::vector<wchar_t>::size_type cap = c1.capacity();   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        cap, c1.size() <= cap);   
    c1.reserve(cap + 5);   
    System::Console::WriteLine("capacity() = {0}, ok = {1}",   
        c1.capacity(), cap + 5 <= c1.capacity());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
capacity() = 4, ok = True  
capacity() = 9, ok = True  
```  
  
## <a name="description"></a>説明  
 実際の容量がここに示した長いと、すべての値からによって異なることに注意してください`ok`テストは true を報告します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)