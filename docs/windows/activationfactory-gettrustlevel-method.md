---
title: Activationfactory::gettrustlevel メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4bddc5a453e1c3aac43fe58d105ccef863c67808
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652270"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel メソッド
オブジェクトの信頼レベルを取得、現在**ActivationFactory**をインスタンス化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
### <a name="parameters"></a>パラメーター  
 *trustLvl*  
 この操作が完了したら、信頼レベルのランタイム クラス、 **ActivationFactory**をインスタンス化します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、アサーション エラーが発生したと*trustLvl*に設定されている`FullTrust`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ActivationFactory クラス](../windows/activationfactory-class.md)