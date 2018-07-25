---
title: CreateClassFactory 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 95d08573515bee89fd86d6b37e3982dde2b29978
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870474"
---
# <a name="createclassfactory-function"></a>CreateClassFactory 関数
指定されたクラスのインスタンスを生成するファクトリを作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `flags`  
 1 つまたは複数の組み合わせ[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙値。  
  
 `entry`  
 ポインター、 [CreatorMap](../windows/creatormap-structure.md)パラメーターは初期化と登録の情報を含む`riid`です。  
  
 `riid`  
 インターフェイス ID への参照  
  
 `ppFactory`  
 この操作は、クラス ファクトリへのポインターでは正常に完了します。 場合、  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 場合、アサーション エラーが発生テンプレート パラメーター `Factory` IClassFactory インターフェイスから派生していません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::Details 名前空間](../windows/microsoft-wrl-wrappers-details-namespace.md)