---
title: CFirePropNotifyEvent クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 728f4e973a7ef74dcdbb44150375df235e0d990e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(静的)コントロール プロパティが変更されたコンテナーのシンクに通知します。|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(静的)コントロールのプロパティが変更しようとしていますが、コンテナーのシンクに通知します。|  
  
## <a name="remarks"></a>コメント  
 `CFirePropNotifyEvent` コントロールのプロパティが変更されたかを変更するには、コンテナーのシンクに通知する 2 つのメソッドがあります。  
  
 場合は、制御を実装するクラスから派生`IPropertyNotifySink`、`CFirePropNotifyEvent`メソッドを呼び出すときに呼び出す`FireOnRequestEdit`または`FireOnChanged`です。 コントロール クラスを派生していない場合`IPropertyNotifySink`、これらの関数への呼び出しを返す`S_OK`です。  
  
 コントロールの作成の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="fireonchanged"></a>  CFirePropNotifyEvent::FireOnChanged  
 すべての通知接続[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)インターフェイス (オブジェクトのすべての接続ポイント) 上に、指定したオブジェクトのプロパティが変更されたことです。  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更されたプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールがコネクション ポイントをサポートしていない場合でもの呼び出しが安全です。  
  
##  <a name="fireonrequestedit"></a>  CFirePropNotifyEvent::FireOnRequestEdit  
 すべての通知接続[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)指定したオブジェクトのプロパティが変更されようとしています (オブジェクトのコネクション ポイントがすべて) 上のインターフェイスです。  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更するプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールがコネクション ポイントをサポートしていない場合でもの呼び出しが安全です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
