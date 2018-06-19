---
title: 並べ替え (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::sort
dev_langs:
- C++
helpviewer_keywords:
- sort function [STL/CLR]
ms.assetid: e30f3e97-60c4-4a8e-89f1-75ec056f587a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2a792641fd7587a59691dec20d6f1c4dafd3e6dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163986"
---
# <a name="sort-stlclr"></a>sort (STL/CLR)
指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って配置します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _RanIt> inline  
    void sort(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void sort(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`sort`です。 詳細については、次を参照してください。[並べ替え](../mfc/reference/cmfclistctrl-class.md#sort)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)