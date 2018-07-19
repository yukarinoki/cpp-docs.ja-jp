---
title: Chaininterfaces::verify メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: c83479434a936f32fb0f7367d8cd02c6676c74e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860695"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify メソッド
テンプレート パラメーターによって、各インターフェイスが定義されていることを確認`I0`を通じて`I9`IUnknown や、IInspectable から継承`I0`から継承`I1`を通じて`I9`です。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>コメント  
 検証操作が失敗した場合、`static_assert`エラーを示すエラー メッセージを出力します。  
  
## <a name="remarks"></a>コメント  
 テンプレート パラメーター`I0`と`I1`が必要ですが、およびパラメーター`I2`を通じて`I9`は省略可能です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ChainInterfaces 構造体](../windows/chaininterfaces-structure.md)