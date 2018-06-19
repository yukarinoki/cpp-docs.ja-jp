---
title: remove_copy (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::remove_copy
dev_langs:
- C++
helpviewer_keywords:
- remove_copy function [STL/CLR]
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f119ff86304a125fc9d0012efef3683aa649bf06
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161195"
---
# <a name="removecopy-stlclr"></a>remove_copy (STL/CLR)
ソース範囲からターゲット範囲に要素をコピーしますが、指定された値の要素はコピーされません。残りの要素の順序に影響を及ぼすことはなく、新しいターゲット範囲の末尾を返します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`remove_copy`です。 詳細については、次を参照してください。 [remove_copy](../standard-library/algorithm-functions.md#remove_copy)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)