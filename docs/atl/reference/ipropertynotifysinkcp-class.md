---
title: IPropertyNotifySinkCP クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fddd187dd6df58c4013b9c1fc7a08d5f644a0db
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203164"
---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP クラス
このクラスは公開[IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)接続可能なオブジェクトに対するアウトゴーイング インターフェイスとしてインターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IPropertyNotifySinkCP`します。  
  
 *CDV*  
 接続ポイントとそのシンク間の接続を管理するクラス。 既定値は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)接続を制限しないことができます。 使用することも[CComUnkArray](../../atl/reference/ccomunkarray-class.md)、固定接続数を指定します。  
  
## <a name="remarks"></a>Remarks  
 `IPropertyNotifySinkCP` すべてのメソッドを通じて、その基底クラスを継承[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)します。  
  
 [IPropertyNotifySink](/windows/desktop/api/ocidl/nn-ocidl-ipropertynotifysink)インターフェイスでは、シンク オブジェクトのプロパティの変更に関する通知を受信できます。 クラス`IPropertyNotifySinkCP`接続可能なオブジェクトに対するアウトゴーイング インターフェイスとしてこのインターフェイスを公開します。 クライアントを実装する必要があります、`IPropertyNotifySink`シンク上のメソッド。  
  
 クラスを派生`IPropertyNotifySinkCP`を表す接続ポイントを作成する場合、`IPropertyNotifySink`インターフェイス。  
  
 ATL でのコネクション ポイントの使用に関する詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPointImpl クラス](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl クラス](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
