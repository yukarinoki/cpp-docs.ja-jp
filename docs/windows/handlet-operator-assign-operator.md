---
title: Handlet::operator = 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a13e8eb7e74625e185b59816b5794b0390e95e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873928"
---
# <a name="handletoperator-operator"></a>HandleT::operator= 演算子
指定した HandleT オブジェクトの値を現在 HandleT オブジェクトに移動します。  
  
## <a name="syntax"></a>構文  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `h`  
 ハンドルを右辺値の参照。  
  
## <a name="return-value"></a>戻り値  
 現在の HandleT オブジェクトへの参照。  
  
## <a name="remarks"></a>コメント  
 この操作には、パラメーターで指定された HandleT オブジェクトが無効になります。`h`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HandleT クラス](../windows/handlet-class.md)