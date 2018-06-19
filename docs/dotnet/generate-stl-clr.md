---
title: 生成 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::generate
dev_langs:
- C++
helpviewer_keywords:
- generate function [STL/CLR]
ms.assetid: 970f209f-31db-47c4-a0bb-4c3e579adb52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ec425853f515500b68594d2890bcc9cc76410fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105954"
---
# <a name="generate-stlclr"></a>generate (STL/CLR)
範囲内の各要素に関数オブジェクトによって生成される値を割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _FwdIt, class _Fn0> inline  
    void generate(_FwdIt _First, _FwdIt _Last, _Fn0 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリ関数と同じ`generate`です。 詳細については、次を参照してください。[生成](../standard-library/algorithm-functions.md#generate)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext アルゴリズム/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)