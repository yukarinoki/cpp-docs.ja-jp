---
title: Comptr::operator::booltype 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d5efd641e5c908e5f1c4d4a3cdb78cd146b634f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 演算子
ComPtr がインターフェイスのオブジェクト有効期間を管理しているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>戻り値  
 インターフェイスのアドレス、この ComPtr に関連付けられているかどうか、 [boolstruct::member](../windows/boolstruct-member-data-member.md)データ メンバー以外の場合、`nullptr`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::Get メソッド](../windows/comptr-get-method.md)