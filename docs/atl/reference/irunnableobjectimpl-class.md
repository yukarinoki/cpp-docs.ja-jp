---
title: IRunnableObjectImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl
- ATLCTL/ATL::IRunnableObjectImpl::GetRunningClass
- ATLCTL/ATL::IRunnableObjectImpl::IsRunning
- ATLCTL/ATL::IRunnableObjectImpl::LockRunning
- ATLCTL/ATL::IRunnableObjectImpl::Run
- ATLCTL/ATL::IRunnableObjectImpl::SetContainedObject
dev_langs:
- C++
helpviewer_keywords:
- containers, running controls
- IRunnableObjectImpl class
- IRunnableObject, ATL implementation
- controls [ATL], running
- controls [C++], container running in ATL
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a08fec0fd38e30729c9131def1831e5e5d8f633e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364116"
---
# <a name="irunnableobjectimpl-class"></a>IRunnableObjectImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IRunnableObjectImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IRunnableObjectImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IRunnableObjectImpl::GetRunningClass](#getrunningclass)|実行中のコントロールの CLSID を返します。 ATL の実装では、CLSID を設定`GUID_NULL`し、返します**E_UNEXPECTED**です。|  
|[IRunnableObjectImpl::IsRunning](#isrunning)|コントロールが実行されているかどうかを判断します。 ATL の実装を返します**TRUE**です。|  
|[IRunnableObjectImpl::LockRunning](#lockrunning)|実行中の状態にコントロールをロックします。 ATL の実装を返します`S_OK`です。|  
|[IRunnableObjectImpl::Run](#run)|コントロールが実行を強制します。 ATL の実装を返します`S_OK`です。|  
|[IRunnableObjectImpl::SetContainedObject](#setcontainedobject)|コントロールが埋め込まれていることを示します。 ATL の実装を返します`S_OK`です。|  
  
## <a name="remarks"></a>コメント  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783)インターフェイス コントロールが実行されているかどうかは、アプリケーションは強制的に実行、または実行中の状態にロックするためのコンテナーを有効にします。 クラス`IRunnableObjectImpl`このインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getrunningclass"></a>  IRunnableObjectImpl::GetRunningClass  
 実行中のコントロールの CLSID を返します。  
  
```
HRESULT GetRunningClass(LPCLSID lpClsid);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装設定\* *lpClsid*に`GUID_NULL`し、返します**E_UNEXPECTED**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::GetRunningClass](http://msdn.microsoft.com/library/windows/desktop/ms693734) Windows SDK にします。  
  
##  <a name="isrunning"></a>  IRunnableObjectImpl::IsRunning  
 コントロールが実行されているかどうかを判断します。  
  
```
virtual BOOL IsRunning();
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します**TRUE**です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::IsRunning](http://msdn.microsoft.com/library/windows/desktop/ms678496) Windows SDK にします。  
  
##  <a name="lockrunning"></a>  IRunnableObjectImpl::LockRunning  
 実行中の状態にコントロールをロックします。  
  
```
HRESULT LockRunning(BOOL fLock, BOOL fLastUnlockCloses);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::LockRunning](http://msdn.microsoft.com/library/windows/desktop/ms693361) Windows SDK にします。  
  
##  <a name="run"></a>  IRunnableObjectImpl::Run  
 コントロールが実行を強制します。  
  
```
HRESULT Run(LPBINDCTX lpbc);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::Run](http://msdn.microsoft.com/library/windows/desktop/ms694517) Windows SDK にします。  
  
##  <a name="setcontainedobject"></a>  IRunnableObjectImpl::SetContainedObject  
 コントロールが埋め込まれていることを示します。  
  
```
HRESULT SetContainedObject(BOOL fContained);
```  
  
### <a name="return-value"></a>戻り値  
 ATL の実装を返します`S_OK`です。  
  
### <a name="remarks"></a>コメント  
 参照してください[IRunnableObject::SetContainedObject](http://msdn.microsoft.com/library/windows/desktop/ms693710) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
