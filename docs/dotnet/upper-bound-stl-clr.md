---
title: upper_bound (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::upper_bound
dev_langs:
- C++
helpviewer_keywords:
- upper_bound function [STL/CLR]
ms.assetid: a377a77b-8005-496e-85ae-b431a9b2f0b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be87a8a91f91e3bdb4417f8ec6f0ab0c51a515cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="upperbound-stlclr"></a>upper_bound (STL/CLR)
順序の基準が二項述語で指定できる場合に、順序付けられた範囲内で、指定した値を超える値を持つ最初の要素の位置を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Ty> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _FwdIt upper_bound(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`upper_bound`です。 詳細については、次を参照してください。 [upper_bound](../standard-library/algorithm-functions.md#upper_bound)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)