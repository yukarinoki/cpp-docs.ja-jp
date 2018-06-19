---
title: 塗りつぶし (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::fill
dev_langs:
- C++
helpviewer_keywords:
- fill function
ms.assetid: eb67241c-9bb3-497e-bec6-639900c60758
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2e1feaba4690bf64d28a7359b3be17d7e70a96f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107439"
---
# <a name="fill-stlclr"></a>fill (STL/CLR)
指定された範囲のすべての要素に同じ新しい値を割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Ty> inline  
    void fill(_FwdIt _First, _FwdIt _Last, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`fill`です。 詳細については、次を参照してください。 [fill](../standard-library/algorithm-functions.md#fill)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)