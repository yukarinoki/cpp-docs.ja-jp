---
title: equal_range (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range function [STL/CLR]
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9001d4b39b1b20e2caa7b5d81ac3b06d42042071
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105869"
---
# <a name="equalrange-stlclr"></a>equal_range (STL/CLR)
順序付けられた範囲内で、最初の位置が指定された要素の位置以下で、2 番目の位置が要素の位置を超える位置のペアを検索します。ここで、シーケンス内の位置を確立するために使用される等価または順序付けの意味は、二項述語によって指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`equal_range`です。 詳細については、次を参照してください。 [equal_range](../standard-library/algorithm-functions.md#equal_range)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)