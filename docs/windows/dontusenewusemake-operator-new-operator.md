---
title: Dontusenewusemake::operator new 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9785ea27c79ff0a118ff3697a22804c520b265ee
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new 演算子
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `__unnamed0`  
 割り当てるメモリのバイト数を指定する名前のないパラメーター。  
  
 `placement`  
 割り当てられる型。  
  
## <a name="return-value"></a>戻り値  
 演算子をオーバー ロードする場合は、追加の引数を渡す方法を提供`new`です。  
  
## <a name="remarks"></a>コメント  
 演算子をオーバー ロード`new`と RuntimeClass で使用されていることを防ぎます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [DontUseNewUseMake クラス](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)