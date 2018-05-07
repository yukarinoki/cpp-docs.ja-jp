---
title: range_adapter::range_adapter (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::range_adapter::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- range_adapter member [STL/CLR]
ms.assetid: b16af13f-3358-4e82-927d-d0d4986bcb18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ea75595e1cdb1f665e5084973e25ca52e4d510eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="rangeadapterrangeadapter-stlclr"></a>range_adapter::range_adapter (STL/CLR)
アダプター オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
range_adapter();  
range_adapter(range_adapter<Iter>% right);  
range_adapter(range_adapter<Iter>^ right);  
range_adapter(Iter first, Iter last);  
```  
  
#### <a name="parameters"></a>パラメーター  
 先頭  
 ラップする最初の反復子。  
  
 last  
 ラップする 2 つ目の反復子。  
  
 右  
 コピーするオブジェクト。  
  
## <a name="remarks"></a>コメント  
 : コンス トラクター  
  
 `range_adapter();`  
  
 既定で構築される反復子を持つ格納された反復子のペアを初期化します。  
  
 : コンス トラクター  
  
 `range_adapter(range_adapter<Iter>% right);`  
  
 格納されている組み合わせをコピーして格納された反復子のペアを初期化`right`です。  
  
 : コンス トラクター  
  
 `range_adapter(range_adapter<Iter>^ right);`  
  
 格納されている組み合わせをコピーして格納された反復子のペアを初期化`*right`です。  
  
 : コンス トラクター  
  
 `range_adapter(Iter^ first, last);`  
  
 格納された反復子のペアを初期化します`first`と`last`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_range_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// construct an empty adapter   
    Myrange c1;   
  
// construct with an iterator pair   
    Myrange c2(d1.begin(), d1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another adapter   
    Myrange c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying an adapter handle   
    Myrange c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
a b c  
a b c  
a b c  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アダプター/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [range_adapter::operator= (STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)