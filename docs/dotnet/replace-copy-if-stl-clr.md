---
title: replace_copy_if (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::replace_copy_if
dev_langs:
- C++
helpviewer_keywords:
- replace_copy_if function [STL/CLR]
ms.assetid: 60edf9b8-34e6-4d94-a611-363ef7b7fb80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f7c266e99b5ef86b8c85c23c77a0ed3cbd2dfcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161747"
---
# <a name="replacecopyif-stlclr"></a>replace_copy_if (STL/CLR)
ソース範囲内の各要素が指定された述語を満たすかどうかを調べ、満たす場合は置き換えて結果を新しいターゲット範囲にコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt, class _Pr, class _Ty> inline  
    _OutIt replace_copy_if(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`replace_copy_if`です。 詳細については、次を参照してください。 [replace_copy_if](../standard-library/algorithm-functions.md#replace_copy_if)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)