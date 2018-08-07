---
title: Ftmbase::unmarshalinterface メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7b34f1af7734fa22db3a9f296bc021917356f8a
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570029"
---
# <a name="ftmbaseunmarshalinterface-method"></a>FtmBase::UnmarshalInterface メソッド
新しく作成されたプロキシを初期化し、そのプロキシにインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pStm*  
 インターフェイス ポインターのマーシャ リングする元となるストリームへのポインター。  
  
 *riid*  
 マーシャ リングするインターフェイスの識別子への参照。  
  
 *ppv*  
 ときにこの操作が完了したらで要求されたインターフェイス ポインターを受け取るポインター変数のアドレス*riid*します。 この操作が成功した場合 **ppv*マーシャ リングするインターフェイスの要求されたインターフェイス ポインターが含まれています。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、または E_FAIL E_NOINTERFACE します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ftm.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [FtmBase クラス](../windows/ftmbase-class.md)