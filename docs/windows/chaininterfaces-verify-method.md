---
title: Chaininterfaces::verify メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b71581687ec69a4aff85f649e85ebfe10c0a844f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650470"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify メソッド
各インターフェイスは、テンプレート パラメーターで定義されていることを確認します*I0*を通じて*I9*から継承`IUnknown`や`IInspectable`、および*I0*から継承。*I1*を通じて*I9*します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Remarks  
 検証操作に失敗した場合、 **static_assert**エラーを説明するエラー メッセージを出力します。  
  
## <a name="remarks"></a>Remarks  
 テンプレート パラメーター *I0*と*I1*が必要なパラメーターと*I2*を通じて*I9*は省略可能です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)