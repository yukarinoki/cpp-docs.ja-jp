---
title: lower_bound (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::lower_bound
dev_langs:
- C++
helpviewer_keywords:
- lower_bound function [STL/CLR]
ms.assetid: 841b70b5-1f54-4ecf-8faa-7dda32a24c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57af2cc34a42543364e59a49aafcd625da720f9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129812"
---
# <a name="lowerbound-stlclr"></a>lower_bound (STL/CLR)
二項述語によって順序の基準を指定することがあります、指定した値以下のと同じ値を持つ順序付けられた範囲内の最初の要素の位置を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt lower_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`lower_bound`です。 詳細については、次を参照してください。 [lower_bound](../standard-library/algorithm-functions.md#lower_bound)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)