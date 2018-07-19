---
title: CFirePropNotifyEvent クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20fd9c660f036c04ea2ca7d06d04315391504e3e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881530"
---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent クラス
このクラスは、コントロール プロパティの変更について、コンテナーのシンクに通知するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(静的)コントロールのプロパティが変更されたコンテナーのシンクに通知します。|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(静的)コントロールのプロパティが変更しようとしていますが、コンテナーのシンクに通知します。|  
  
## <a name="remarks"></a>Remarks  
 `CFirePropNotifyEvent` コントロールのプロパティが変更されたかを変更するには、コンテナーのシンクに通知する 2 つのメソッドがあります。  
  
 場合は、制御を実装するクラスから派生`IPropertyNotifySink`、`CFirePropNotifyEvent`メソッドを呼び出すときに呼び出す`FireOnRequestEdit`または`FireOnChanged`します。 コントロール クラスを派生していない場合`IPropertyNotifySink`、これらの関数の呼び出しが S_OK を返します。  
  
 コントロールの作成の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 すべての通知接続[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)インターフェイス (オブジェクトの接続ポイントがすべて) 上に、指定したオブジェクトのプロパティが変更されました。  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更されたプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 この関数は、コントロールが接続ポイントをサポートしていない場合でも呼び出しが安全です。  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 すべての通知接続されている[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)インターフェイス (上、オブジェクトの接続ポイントがすべて)、指定したオブジェクトのプロパティが変更されようにします。  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更するプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 この関数は、コントロールが接続ポイントをサポートしていない場合でも呼び出しが安全です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
