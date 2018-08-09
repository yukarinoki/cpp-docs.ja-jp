---
title: Module::getclassobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 08b96712b2e66ebf527ccb1cbf408c2a7d028b60
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012077"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject メソッド
クラス ファクトリのキャッシュを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *clsid*  
 クラスの id。  
  
 *riid*  
 要求したインターフェイス ID です。  
  
 *ppv*  
 返されるオブジェクトへのポインター。  
  
 *サーバー名*  
 いずれかで指定されているサーバー名、 `ActivatableClassWithFactory`、 `ActivatableClassWithFactoryEx`、または`ActivatableClass`マクロ; または**nullptr**を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、Windows ランタイムではなく COM にのみ使用します。 このメソッドを公開のみ`IClassFactory`メソッド。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)