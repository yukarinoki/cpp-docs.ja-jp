---
title: make_pair (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::make_pair
dev_langs:
- C++
helpviewer_keywords:
- make_pair function [STL/CLR]
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 99e2cc7bc7255940b28f2f85dae1a7cbebd6df46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33134989"
---
# <a name="makepair-stlclr"></a>make_pair (STL/CLR)
ように、`pair`値のペアからです。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Value1`  
 最初のラップされた値の型。  
  
 `Value2`  
 2 番目のラップされた値の型。  
  
 `first`  
 ラップする最初の値。  
  
 `second`  
 2 番目の値をラップします。  
  
## <a name="remarks"></a>コメント  
 このテンプレート関数は `pair<Value1, Value2>(first, second)` を返します。 構築するために使用する、`pair<Value1, Value2>`値のペアからのオブジェクト。  
  
## <a name="example"></a>例  
  
```cpp  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[y, 4]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)