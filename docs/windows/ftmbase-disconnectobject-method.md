---
title: Ftmbase::disconnectobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs:
- C++
helpviewer_keywords:
- DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bb6b6be87736d55eabc6b487101ec68fc16e378
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646141"
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject メソッド
オブジェクトへのすべての外部接続が強制的に解放します。 オブジェクトのサーバーでは、シャット ダウンする前に、このメソッドのオブジェクトの実装を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
### <a name="parameters"></a>パラメーター  
 *dwReserved*  
 今後使用するために予約されています。0 にする必要があります。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)