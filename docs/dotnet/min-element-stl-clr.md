---
title: min_element (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::min_element
dev_langs:
- C++
helpviewer_keywords:
- min_element function [STL/CLR]
ms.assetid: 2a9c6828-9722-454f-9c10-d4a184d4d21b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 27bfa9632a4145bc93d20a43b873bdfcdd498a2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130244"
---
# <a name="minelement-stlclr"></a>min_element (STL/CLR)
指定された範囲内の最小の要素の最初の出現箇所を検索します。順序の基準は二項述語によって指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt min_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`min_element`です。 詳細については、次を参照してください。 [min_element](../standard-library/algorithm-functions.md#min_element)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)