---
title: CreateActivationFactory 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 780fd8b6866af05007d9c99e3165b149eab956bd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642904"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory 関数
Windows ランタイムによるアクティブ化が可能な、指定されたクラスのインスタンスを生成するファクトリを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *flags*  
 1 つ以上を組み合わせた[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。  
  
 *entry*  
 ポインターを[CreatorMap](../windows/creatormap-structure.md)パラメーターに関する情報を初期化し、登録を含む*riid*します。  
  
 *riid*  
 インターフェイス ID への参照  
  
 *ppFactory*  
 この操作は、アクティベーション ファクトリへのポインターでは正常に完了します。 場合、  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>Remarks  
 場合は、アサート エラーが出力テンプレート パラメーター*ファクトリ*インターフェイスから派生していない`IActivationFactory`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)