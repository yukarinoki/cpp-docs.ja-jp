---
title: IOleControlImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IOleControlImpl
- ATLCTL/ATL::IOleControlImpl
- ATLCTL/ATL::IOleControlImpl::FreezeEvents
- ATLCTL/ATL::IOleControlImpl::GetControlInfo
- ATLCTL/ATL::IOleControlImpl::OnAmbientPropertyChange
- ATLCTL/ATL::IOleControlImpl::OnMnemonic
dev_langs:
- C++
helpviewer_keywords:
- IOleControlImpl class
ms.assetid: 5a4255ad-ede4-49ca-ba9a-07c2e919fa85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a54067f53e83d78f063ae5f3694460452e24b26
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361799"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス
このクラスの既定の実装を提供する、 **IOleControl**インターフェイスと実装**IUnknown**です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IOleControlImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|コンテナーを無視するか、コントロールからのイベントを受け付けるかどうかを示します。|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|コントロールのキーボードの動作に関する情報を入力します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|1 つまたは複数のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。 ATL の実装を返します`S_OK`です。|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。 ATL の実装を返します**E_NOTIMPL**です。|  
  
## <a name="remarks"></a>コメント  
 クラス`IOleControlImpl`の既定の実装を提供、 [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320)インターフェイスと実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 ATL の実装で`FreezeEvents`コントロール クラスのインクリメント`m_nFreezeEvents`データ メンバー場合`bFreeze`は**TRUE**、およびデクリメント`m_nFreezeEvents`場合`bFreeze`は**FALSE**.  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>コメント  
 `FreezeEvents` 返します`S_OK`です。  
  
 参照してください[:freezeevents](http://msdn.microsoft.com/library/windows/desktop/ms678482) Windows SDK にします。  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 コントロールのキーボードの動作に関する情報を入力します。  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 1 つまたは複数のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>戻り値  
 `S_OK` を返します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) Windows SDK にします。  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>戻り値  
 返します**E_NOTIMPL**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)
