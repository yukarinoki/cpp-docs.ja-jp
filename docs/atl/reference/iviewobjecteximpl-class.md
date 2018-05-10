---
title: クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c51bc9e5feb02d837c37341b82a1fc19a3cea558
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="iviewobjecteximpl-class"></a>クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IViewObjectExImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|デバイス コンテキストにコントロールの内部表現を描画します。|  
|[IViewObjectExImpl::Freeze](#freeze)|コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`です。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|1 つを使用する必要がある場合は、コントロールで、既存アドバイズ シンクの接続を取得します。|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|コントロールによって描画に使用する論理パレットを返します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IViewObjectExImpl::GetExtent](#getextent)|コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)です。|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|ユーザーによるそれを使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。|  
|[IViewObjectExImpl::GetRect](#getrect)|要求された描画範囲を示す四角形を返します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|オブジェクトとどのような描画の側面がサポートされている不透明度に関する情報を返します。|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|セルのかどうか、指定したポイントで指定した四角形を返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|セルのかどうか、コントロールの表示長方形で指定した位置四角形と重なっているを返します、**中**値`pHitResult`です。|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|シンクは、コントロールのビューでの変更について通知できるように、コントロールとアドバイズ シンク間の接続を設定します。|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|コントロールの描画の表示を解除します。 ATL の実装を返します**E_NOTIMPL**です。|  
  
## <a name="remarks"></a>コメント  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイス自体を直接表示および作成および管理に通知するアドバイズ シンクするコントロールを有効にしますコントロールの表示の変更のコンテナーです。 **IViewObjectEx**インターフェイスでは、ちらつきなしの描画、四角形では非透過的なコントロール、ヒット テスト (たとえば、どの程度近いかマウスをクリックする必要がありますで考慮するなどのコントロール拡張機能のサポートコントロールで)。 クラス`IViewObjectExImpl`これらのインターフェイスの既定の実装を提供し、実装**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 デバイス コンテキストにコントロールの内部表現を描画します。  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す**CComControl::OnDrawAdvanced**をさらに、コントロール クラスの`OnDraw`メソッドです。 `OnDraw`メソッドは ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的に、コントロール クラスに追加します。 ウィザードの既定`OnDraw`ラベル"ATL 3.0"四角形を描画します。  
  
 参照してください[IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK にします。  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`です。 ATL の実装を返します**E_NOTIMPL**です。  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) Windows SDK にします。  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 1 つを使用する必要がある場合は、コントロールで、既存アドバイズ シンクの接続を取得します。  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>コメント  
 アドバイズ シンクがコントロール クラスのデータ メンバーに格納されている[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)です。  
  
 参照してください[IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) Windows SDK にします。  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 コントロールによって描画に使用する論理パレットを返します。 ATL の実装を返します**E_NOTIMPL**です。  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) Windows SDK にします。  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)です。  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK にします。  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 ユーザーによるそれを使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>コメント  
 場合`dwAspect`は`DVASPECT_CONTENT`と*pExtentInfo dwExtentMode]-> [* は**DVEXTENT_CONTENT**、設定 *`psizel`コントロール クラスのデータ メンバーに[CComControlBase:: m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)です。 それ以外の場合はエラーを返します`HRESULT`です。  
  
 参照してください[IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) Windows SDK にします。  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 要求された描画範囲を示す四角形を返します。 ATL の実装を返します**E_NOTIMPL**です。  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) Windows SDK にします。  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 オブジェクトとどのような描画の側面がサポートされている不透明度に関する情報を返します。  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>コメント  
 既定で、ATL 設定`pdwStatus`コントロールをサポートしていることを示すために**VIEWSTATUS_OPAQUE** (使用できる値は、[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)列挙型)。  
  
 参照してください[IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) Windows SDK にします。  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 セルのかどうか、指定したポイントで指定した四角形を返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>コメント  
 値には、いずれかを指定できる**この**または**値**です。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)、メソッドを返します`S_OK`です。 メソッドを返しますそれ以外の場合、 **E_FAIL**です。  
  
 参照してください[IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) Windows SDK にします。  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 セルのかどうか、コントロールの表示長方形で指定した位置四角形と重なっているを返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>コメント  
 値には、いずれかを指定できる**この**または**値**です。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)、メソッドを返します`S_OK`です。 メソッドを返しますそれ以外の場合、 **E_FAIL**です。  
  
 参照してください[IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) Windows SDK にします。  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 シンクは、コントロールのビューでの変更について通知できるように、コントロールとアドバイズ シンク間の接続を設定します。  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>コメント  

 ポインター、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)アドバイズ シンクのインターフェイスは、コントロール クラスのデータ メンバーに格納されている[アドバイズ](ccomcontrolbase-class.md#m_spadvisesink)です。  

  
 参照してください[IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) Windows SDK にします。  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 コントロールの描画の表示を解除します。 ATL の実装を返します**E_NOTIMPL**です。  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641) Windows SDK にします。  
  
##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle  
 このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>パラメーター  
 *hHandle*  
 終了するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡されたハンドルはへの呼び出しによって、このオブジェクトに以前関連付けられていた[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::CloseHandle`です。  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwParam`  
 ユーザーのパラメーターです。  
  
 `hObject`  
 シグナル状態になるハンドルです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時にエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡される DWORD/ポインター、ハンドルされたへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
### <a name="example"></a>例  
 次のコードは、の簡単な実装を示しています。`IWorkerThreadClient::Execute`です。  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [チュートリアル](../../atl/active-template-library-atl-tutorial.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
