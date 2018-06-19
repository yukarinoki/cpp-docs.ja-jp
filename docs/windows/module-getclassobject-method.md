---
title: Module::getclassobject メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 9205b04fc27e1c6e0e6133a08c3c2f69ffdfc314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878539"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject メソッド
クラス ファクトリのキャッシュを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clsid`  
 クラスの id。  
  
 `riid`  
 要求するインターフェイス ID です。  
  
 `ppv`  
 返されるオブジェクトへのポインター。  
  
 `serverName`  
 いずれかで指定されているサーバー名、 `ActivatableClassWithFactory`、 `ActivatableClassWithFactoryEx`、または`ActivatableClass`マクロ; または`nullptr`を既定のサーバー名を取得します。  
  
## <a name="return-value"></a>戻り値  
  
## <a name="remarks"></a>コメント  
 このメソッドは Windows ランタイムではなく、COM にのみ使用します。 このメソッドは、IClassFactory メソッドのみを公開します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)