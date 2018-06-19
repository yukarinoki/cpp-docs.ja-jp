---
title: 演算子&gt;= (multiset) (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::multiset::operator>=
dev_langs:
- C++
helpviewer_keywords:
- operator>= member [STL/CLR]
ms.assetid: 978cc521-e810-4f3a-85e7-880d6b45db59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ff9651033054b501303aad502dbf53989ccdb97a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33139474"
---
# <a name="operatorgt-multiset-stlclr"></a>演算子&gt;= (multiset) (STL/CLR)
リストよりも大きいまたは等しい比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Key>  
    bool operator>=(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のコンテナー。  
  
 右  
 比較する右のコンテナー。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(left < right)`です。 テストするために使用するかどうか`left`する前に順序付けされていない`right`がいつ行われる 2 つのマルチセット要素で要素を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_multiset_operator_ge.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
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
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [演算子 = = (multiset) (STL/CLR)](../dotnet/operator-equality-multiset-stl-clr.md)   
 [operator! = (multiset) (STL/CLR)](../dotnet/operator-inequality-multiset-stl-clr.md)   
 [演算子\<(multiset) (STL/CLR)](../dotnet/operator-less-than-multiset-stl-clr.md)   
 [operator > (multiset) (STL/CLR)](../dotnet/operator-greater-than-multiset-stl-clr.md)   
 [operator<= (multiset) (STL/CLR)](../dotnet/operator-less-or-equal-multiset-stl-clr.md)