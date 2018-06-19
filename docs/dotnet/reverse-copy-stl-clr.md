---
title: reverse_copy (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::reverse_copy
dev_langs:
- C++
helpviewer_keywords:
- reverse_copy function [STL/CLR]
ms.assetid: 694e577a-0fa8-44f7-adde-6dd9f45adefd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cdc17fc5dc5b8007bbe1f478e250f31792e76a40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161604"
---
# <a name="reversecopy-stlclr"></a>reverse_copy (STL/CLR)
ターゲット範囲にコピーします。 ソース範囲内の要素の順序を反転します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _BidIt, class _OutIt> inline  
    _OutIt reverse_copy(_BidIt _First, _BidIt _Last, _OutIt _Dest);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`reverse_copy`です。 詳細については、次を参照してください。 [reverse_copy](../standard-library/algorithm-functions.md#reverse_copy)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)