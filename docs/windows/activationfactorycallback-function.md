---
title: ActivationFactoryCallback 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e2e7b2301ae4dd38a40bdf4583e963e55a8b12d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461394"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback 関数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *activationId*  
 ランタイム クラス名を指定する文字列へのハンドルします。  
  
 *ppFactory*  
 ときにこの操作が完了すると、パラメーターに対応するアクティベーション ファクトリ*activationId*します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 可能性の高いエラー Hresult CLASS_E_CLASSNOTAVAILABLE、E_INVALIDARG です。  
  
## <a name="remarks"></a>Remarks  
 指定されたアクティブ化 ID のアクティベーション ファクトリを取得します。  
  
 Windows ランタイムでは、ランタイム クラス名で指定されたオブジェクトを要求するには、このコールバック関数を呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)