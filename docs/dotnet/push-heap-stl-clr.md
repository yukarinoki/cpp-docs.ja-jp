---
title: push_heap (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::push_heap
dev_langs:
- C++
helpviewer_keywords:
- push_heap function [STL/CLR]
ms.assetid: 184fe1d9-5f75-4c11-adbb-84b6b5c8ecd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 12b9763c210eb9aa0480ff51a0be70d60400f6c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="pushheap-stlclr"></a>push_heap (STL/CLR)
範囲の末尾にある要素を、範囲内の以前の要素で構成される既存のヒープに追加します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _RanIt> inline  
    void push_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void push_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`push_heap`です。 詳細については、次を参照してください。 [push_heap](../standard-library/algorithm-functions.md#push_heap)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)