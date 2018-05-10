---
title: Comptr::releaseandgetaddressof メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 32d846a1fc41596812ca6e8578f25f9ae8115182
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf メソッド
この ComPtr に関連付けられたインターフェイスを解放してから、 [ptr_](../windows/comptr-ptr-data-member.md) データ メンバーのアドレスを取得します。このアドレスには、解放されたインターフェイスへのポインターが含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## <a name="return-value"></a>戻り値  
 アドレス、 [ptr _](../windows/comptr-ptr-data-member.md)この ComPtr のデータ メンバーです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::ptr_ データ メンバー](../windows/comptr-ptr-data-member.md)