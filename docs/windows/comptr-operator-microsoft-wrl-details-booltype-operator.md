---
title: Comptr::operator:details::booltype 演算子 |Microsoft Docs
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
ms.openlocfilehash: 1a4ec737c3f24899e50220c3e862283b88a826b9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461165"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 演算子
示すかどうかを**ComPtr**インターフェイスのオブジェクトの有効期間を管理します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>戻り値  
 インターフェイスに関連付けられている場合**ComPtr**のアドレス、 [boolstruct::member](../windows/boolstruct-member-data-member.md)データ メンバー、それ以外の**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::Get メソッド](../windows/comptr-get-method.md)