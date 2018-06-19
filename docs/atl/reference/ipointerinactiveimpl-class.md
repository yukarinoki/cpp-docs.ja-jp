---
title: IPointerInactiveImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c28eb8d6db520bd1c2d5de5642098263508c0f6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360333"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl クラス
このクラスは実装**IUnknown**と[IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)インターフェイスのメソッドです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IPointerInactiveImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|オブジェクトの現在のアクティブ化ポリシーを取得します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることができますに通知します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|アクティブでないオブジェクトにマウス ポインターを設定します。 ATL の実装を返します**E_NOTIMPL**です。|  
  
## <a name="remarks"></a>コメント  
 非アクティブなオブジェクトは、単に読み込まれたか、実行中である 1 つです。 非アクティブなオブジェクトは、アクティブなオブジェクトとは異なり Windows マウスとキーボード メッセージを受信できません。 したがって、アクティブでないオブジェクトはより少ないリソースを使用してが通常より効率的です。  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712)インターフェイスが非アクティブなままマウスとの対話の最小レベルをサポートするためにオブジェクトを許可します。 この機能は、コントロールに特に便利です。  
  
 クラス`IPointerInactiveImpl`を実装する、`IPointerInactive`メソッドだけを返すことによって**E_NOTIMPL**です。 実装するただし、 **IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy  
 オブジェクトの現在のアクティブ化ポリシーを取得します。  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) Windows SDK にします。  
  
##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove  
 マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることができますに通知します。  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) Windows SDK にします。  
  
##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor  
 アクティブでないオブジェクトにマウス ポインターを設定します。  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
