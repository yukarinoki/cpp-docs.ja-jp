---
title: カウント (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::count
dev_langs:
- C++
helpviewer_keywords:
- count function [STL/CLR]
ms.assetid: 6d10abb4-3c48-469c-804c-281015b12865
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4992874a6bede4e62dc7035ea755a83681a907eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="count-stlclr"></a>count (STL/CLR)
範囲内で値が指定された値と一致する要素の数を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _Ty> inline  
    typename iterator_traits<_InIt>::difference_type  
        count(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`count`です。 詳細については、次を参照してください。[カウント](../standard-library/algorithm-functions.md#count)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)