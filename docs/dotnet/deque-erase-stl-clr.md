---
title: deque::erase (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::erase
dev_langs:
- C++
helpviewer_keywords:
- erase member [STL/CLR]
ms.assetid: 831fbc2b-604f-446b-88bc-b37531304c33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5afcc69c27cf96f31d85b4c48d57540669941cbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dequeerase-stlclr"></a>deque::erase (STL/CLR)
指定した位置にある要素を削除します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `first`  
 消去する範囲の開始しています。  
  
 `last`  
 消去する範囲の終了。  
  
 `where`  
 消去する要素。  
  
## <a name="remarks"></a>コメント  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`where`です。 それを使用するには 1 つの要素を削除します。  
  
 2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 これを使用するには 0 個以上の連続する要素を削除します。  
  
 両方のメンバー関数が、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md) `()`このような要素が存在しない場合。  
  
 要素を消去するには、ときに要素のコピーの数は消去の終了と、シーケンスの最も近い最後の要素の数に比例します。 (シーケンスの先頭または末尾にある 1 つまたは複数の要素を消去するには、ときに要素のコピーは発生しません。)  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_deque_erase.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::deque<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
erase(begin()) = b  
 b c d e  
erase(begin(), end()-1) = e  
size() = 1  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)