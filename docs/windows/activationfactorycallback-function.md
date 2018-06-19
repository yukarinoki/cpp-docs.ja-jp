---
title: ActivationFactoryCallback 関数 |Microsoft ドキュメント
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
ms.openlocfilehash: 2f1bae2c503f4e5f0c887a46956248184ece9a1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857325"
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
 `activationId`  
 ランタイム クラス名を指定する文字列へのハンドルします。  
  
 `ppFactory`  
 この操作の完了時、パラメーターに対応するアクティベーション ファクトリ`activationId`です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 可能性の高いエラー Hresult は、CLASS_E_CLASSNOTAVAILABLE および E_INVALIDARG です。  
  
## <a name="remarks"></a>コメント  
 指定されたアクティブ化 ID のアクティベーション ファクトリを取得します  
  
 Windows ランタイムでは、そのランタイム クラス名で指定されたオブジェクトを要求するには、このコールバック関数を呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)