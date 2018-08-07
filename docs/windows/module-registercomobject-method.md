---
title: Module::registercomobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterCOMObject method
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c997b4221dee913a6eaad55f6f114b0ad9d820e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606541"
---
# <a name="moduleregistercomobject-method"></a>Module::RegisterCOMObject メソッド
他のアプリケーションがそれらに接続できるように、1 つまたは複数の COM オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
### <a name="parameters"></a>パラメーター  
 *サーバー名*  
 サーバーの完全修飾名。  
  
 *clsid*  
 登録する Clsid の配列。  
  
 *ファクトリ*  
 パブリッシュされるかどうかをクラスのオブジェクトの IUnknown インターフェイスの配列。  
  
 *Cookie*  
 操作が完了したらは、登録され、そのオブジェクト クラスを識別する値へのポインターの配列。 これらの値は使用後で登録を取り消します。  
  
 *count*  
 登録する Clsid の数。  
  
## <a name="return-value"></a>戻り値  
 S_OK 場合成功します。それ以外の場合、HRESULT を理由を示す CO_E_OBJISREG など、操作に失敗しました。  
  
## <a name="remarks"></a>Remarks  
 COM オブジェクトは、CLSCTX 列挙型の別個の列挙子に登録されます。  
  
 登録済みのオブジェクトへの接続の種類が現在の組み合わせで指定された*comflag*テンプレート パラメーターと REGCLS 列挙体の REGCLS_SUSPENDED 列挙子。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)