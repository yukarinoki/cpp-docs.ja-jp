---
title: vector::resize (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector::resize
dev_langs:
- C++
helpviewer_keywords:
- resize member [STL/CLR]
ms.assetid: a3556fbc-67d9-463a-9ffc-cb43ee15657f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f7327b62906746ef3bb561d88f8c6ddc2134aa65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="vectorresize-stlclr"></a>vector::resize (STL/CLR)
要素の数を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### <a name="parameters"></a>パラメーター  
 new_size  
 被制御シーケンスの新しいサイズ。  
  
 val  
 埋め込み要素の値です。  
  
## <a name="remarks"></a>コメント  
 メンバー関数の両方では、ことを確認[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `()`記す返します`new_size`です。 被制御シーケンスを長くする必要がある場合、最初のメンバー関数では値 `value_type()` で要素を追加し、2 番目のメンバー関数では値 `val` で要素を追加します。 被制御シーケンスを短くするために、メンバー関数はどちら効果的に消去の最後の要素[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md) `() -` `new_size`回です。 被制御シーケンスがサイズであることを確認するために使用`new_size`トリミングまたは現在の被制御シーケンスの余白で、します。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_resize.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::vector<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 0 0 0 0  
size() = 0  
 x x x x x  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)   
 [vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)   
 [vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)