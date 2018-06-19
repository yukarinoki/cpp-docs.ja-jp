---
title: min (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::min
dev_langs:
- C++
helpviewer_keywords:
- min function [STL/CLR]
ms.assetid: 7a2c82d1-424c-48a9-a944-adcf95511aef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5449af49537a2a7633048415d06217edbc64783d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33131960"
---
# <a name="min-stlclr"></a>min (STL/CLR)
2 つのオブジェクトを比較し、小さい方のオブジェクトを返します。順序の基準は、二項述語によって指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _Ty> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty min(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`min`です。 詳細については、次を参照してください。 [min](../standard-library/algorithm-functions.md#min)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)