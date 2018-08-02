---
title: Comptr::releaseandgetaddressof メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d55241ddefce0e4fcd7f72698779d6e4ec97e20
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464994"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf メソッド
これに関連付けられているインターフェイスを解放**ComPtr**しのアドレスを取得し、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバーは、リリースされたインターフェイスへのポインターが含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>戻り値  
 アドレス、 [ptr _](../windows/comptr-ptr-data-member.md)データ メンバー **ComPtr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)