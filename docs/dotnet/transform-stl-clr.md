---
title: 変換 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::transform
dev_langs:
- C++
helpviewer_keywords:
- transform function [STL/CLR]
ms.assetid: 08940969-6d10-40e4-a35b-68dd801b3949
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2301cfbdcd60d60541c0240ced59d44a844b502f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="transform-stlclr"></a>変換 (STL/CLR)
指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をターゲット範囲にコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt, class _Fn1> inline  
    _OutIt transform(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Fn1 _Func);  
template<class _InIt1, class _InIt2, class _OutIt, class _Fn2> inline  
    _OutIt transform(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`transform`です。 詳細については、次を参照してください。[変換](../standard-library/algorithm-functions.md#transform)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)