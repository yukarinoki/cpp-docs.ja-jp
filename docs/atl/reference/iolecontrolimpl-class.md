---
title: IOleControlImpl クラス |Microsoft Docs
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
ms.openlocfilehash: 34bdb0af5965b300e77a02858af3708c90fa63d0
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879284"
---
# <a name="iolecontrolimpl-class"></a>IOleControlImpl クラス
このクラスの既定の実装を提供する、`IOleControl`インターフェイスと実装`IUnknown`します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleControlImpl
```   
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IOleControlImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleControlImpl::FreezeEvents](#freezeevents)|コンテナーを無視するか、コントロールからのイベントを受け取るかどうかを示します。|  
|[IOleControlImpl::GetControlInfo](#getcontrolinfo)|コントロールのキーボード動作に関する情報が表示されます。 ATL の実装では、E_NOTIMPL を返します。|  
|[IOleControlImpl::OnAmbientPropertyChange](#onambientpropertychange)|1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。 ATL の実装では、S_OK を返します。|  
|[IOleControlImpl::OnMnemonic](#onmnemonic)|ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。 ATL の実装では、E_NOTIMPL を返します。|  
  
## <a name="remarks"></a>Remarks  
 クラス`IOleControlImpl`の既定の実装を提供します、 [IOleControl](http://msdn.microsoft.com/library/windows/desktop/ms694320)インターフェイスと実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleControl`  
  
 `IOleControlImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="freezeevents"></a>  IOleControlImpl::FreezeEvents  
 ATL の実装で`FreezeEvents`コントロール クラスのインクリメント`m_nFreezeEvents`データ メンバー場合`bFreeze`が true の場合、およびデクリメント`m_nFreezeEvents`場合`bFreeze`は FALSE です。  
  
```
HRESULT FreezeEvents(BOOL bFreeze);
```  
  
### <a name="remarks"></a>Remarks  
 `FreezeEvents` S_OK を返します。  
  
 参照してください[:freezeevents](http://msdn.microsoft.com/library/windows/desktop/ms678482) Windows SDK にします。  
  
##  <a name="getcontrolinfo"></a>  IOleControlImpl::GetControlInfo  
 コントロールのキーボード動作に関する情報が表示されます。  
  
```
HRESULT GetControlInfo(LPCONTROLINFO pCI);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleControl:GetControlInfo](http://msdn.microsoft.com/library/windows/desktop/ms693730) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
##  <a name="onambientpropertychange"></a>  IOleControlImpl::OnAmbientPropertyChange  
 1 つ以上のコンテナーのアンビエント プロパティが変更されたことをコントロールに通知します。  
  
```
HRESULT OnAmbientPropertyChange(DISPID dispid);
```  
  
### <a name="return-value"></a>戻り値  
 S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleControl::OnAmbientPropertyChange](http://msdn.microsoft.com/library/windows/desktop/ms690175) Windows SDK にします。  
  
##  <a name="onmnemonic"></a>  IOleControlImpl::OnMnemonic  
 ユーザーが指定されたキーストロークを押されたことをコントロールに通知します。  
  
```
HRESULT OnMnemonic(LPMSG pMsg);
```  
  
### <a name="return-value"></a>戻り値  
 E_NOTIMPL を返します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[IOleControl::OnMnemonic](http://msdn.microsoft.com/library/windows/desktop/ms680699) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [IOleObjectImpl クラス](../../atl/reference/ioleobjectimpl-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [クラスの概要](../../atl/atl-class-overview.md)
