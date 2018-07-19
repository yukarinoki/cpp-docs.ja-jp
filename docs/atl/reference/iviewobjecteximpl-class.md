---
title: IViewObjectExImpl クラス |Microsoft Docs
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
ms.openlocfilehash: 3eb40b5b886407a87e0633052cde67868d756a88
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883646"
---
# <a name="iviewobjecteximpl-class"></a>IViewObjectExImpl クラス
このクラスは実装`IUnknown`の既定の実装を提供し、 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイス。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、`IViewObjectExImpl`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|デバイス コンテキストにコントロールの表現を描画します。|  
|[IViewObjectExImpl::Freeze](#freeze)|コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|コントロールによって描画に使用する論理パレットを返します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IViewObjectExImpl::GetExtent](#getextent)|コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得します。[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更に関するヒントを提供します。|  
|[IViewObjectExImpl::GetRect](#getrect)|要求された描画の外観を示す四角形を返します。 ATL の実装では、E_NOTIMPL を返します。|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|オブジェクトとどのような描画の側面がサポートされているの不透明度についての情報を返します。|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|チェックのかどうか、指定したポイントは指定した四角形では、し、返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`します。|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|コントロールの表示の四角形が任意の時点で、指定した場所の四角形が重複しの中の値を返すかどうかを確認します。`pHitResult`します。|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|コントロールとアドバイズ シンク間の接続設定、シンクにコントロールのビューステートの変化について通知することができます。|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|コントロールの描画の表示を解除します。 ATL の実装では、E_NOTIMPL を返します。|  
  
## <a name="remarks"></a>Remarks  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイス自体を直接表示および作成および管理に通知するアドバイズ シンクするコントロールを有効にしますコントロールの表示の変更のコンテナーです。 `IViewObjectEx`インターフェイスは、描画のちらつきのない、四角形以外と透過的なコントロール、ヒット テスト (たとえば、閉じる方法マウスをクリックする必要があります、コントロールと見なされる) などのコントロール拡張機能のサポートを提供します。 クラス`IViewObjectExImpl`これらのインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlctl.h  
  
##  <a name="draw"></a>  IViewObjectExImpl::Draw  
 デバイス コンテキストにコントロールの表現を描画します。  
  
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
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す`CComControl::OnDrawAdvanced`コントロール クラスのさらに呼び出す`OnDraw`メソッド。 `OnDraw`メソッドは、ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的に、コントロール クラスに追加します。 ウィザードの既定`OnDraw`ラベル"ATL 3.0"四角形を描画します。  
  
 参照してください[IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655) Windows SDK にします。  
  
##  <a name="freeze"></a>  IViewObjectExImpl::Freeze  
 コントロールの描画の表現がフリーズするまで変更できないように、`Unfreeze`します。 ATL の実装では、E_NOTIMPL を返します。  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728) Windows SDK にします。  
  
##  <a name="getadvise"></a>  IViewObjectExImpl::GetAdvise  
 1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>Remarks  
 アドバイズ シンクがコントロールのクラスのデータ メンバーに格納されている[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)します。  
  
 参照してください[IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772) Windows SDK にします。  
  
##  <a name="getcolorset"></a>  IViewObjectExImpl::GetColorSet  
 コントロールによって描画に使用する論理パレットを返します。 ATL の実装では、E_NOTIMPL を返します。  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553) Windows SDK にします。  
  
##  <a name="getextent"></a>  IViewObjectExImpl::GetExtent  
 コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得します。[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032) Windows SDK にします。  
  
##  <a name="getnaturalextent"></a>  IViewObjectExImpl::GetNaturalExtent  
 ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更に関するヒントを提供します。  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>Remarks  
 場合`dwAspect`は DVASPECT_CONTENT と*pExtentInfo dwExtentMode]-> [* DVEXTENT_CONTENT 設定は、*`psizel`コントロール クラスのデータ メンバーに[CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)します。 それ以外の場合、エラーの hresult 値を返します。  
  
 参照してください[IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718) Windows SDK にします。  
  
##  <a name="getrect"></a>  IViewObjectExImpl::GetRect  
 要求された描画の外観を示す四角形を返します。 ATL の実装では、E_NOTIMPL を返します。  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246) Windows SDK にします。  
  
##  <a name="getviewstatus"></a>  IViewObjectExImpl::GetViewStatus  
 オブジェクトとどのような描画の側面がサポートされているの不透明度についての情報を返します。  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>Remarks  
 既定では、ATL の設定`pdwStatus`をコントロールが VIEWSTATUS_OPAQUE をサポートすることを示すために (使用できる値は、[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)列挙型)。  
  
 参照してください[IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371) Windows SDK にします。  
  
##  <a name="queryhitpoint"></a>  IViewObjectExImpl::QueryHitPoint  
 チェックのかどうか、指定したポイントは指定した四角形では、し、返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`します。  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Remarks  
 値には、このまたは値のいずれかを指定できます。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)S_OK が返されます。 それ以外の場合、メソッドは、E_FAIL を返します。  
  
 参照してください[IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209) Windows SDK にします。  
  
##  <a name="queryhitrect"></a>  IViewObjectExImpl::QueryHitRect  
 コントロールの表示の四角形が任意の時点で、指定した場所の四角形が重複し、返すかどうかを確認します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`します。  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>Remarks  
 値には、このまたは値のいずれかを指定できます。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)S_OK が返されます。 それ以外の場合、メソッドは、E_FAIL を返します。  
  
 参照してください[IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797) Windows SDK にします。  
  
##  <a name="setadvise"></a>  IViewObjectExImpl::SetAdvise  
 コントロールとアドバイズ シンク間の接続設定、シンクにコントロールのビューステートの変化について通知することができます。  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>Remarks  

 ポインター、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)アドバイズ シンク上のインターフェイスがコントロールのクラスのデータ メンバーに格納されている[アドバイズ](ccomcontrolbase-class.md#m_spadvisesink)します。  

  
 参照してください[IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950) Windows SDK にします。  
  
##  <a name="unfreeze"></a>  IViewObjectExImpl::Unfreeze  
 コントロールの描画の表示を解除します。 ATL の実装では、E_NOTIMPL を返します。  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>Remarks  
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
 成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドに渡されたハンドルが既に関連付けられているこのオブジェクトへの呼び出しによって[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::CloseHandle`します。  
  
 [!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>  IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態コードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 *について*  
 ユーザー パラメーター。  
  
 *hObject*  
 このハンドルがシグナル状態になります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドに渡された DWORD/ポインター、ハンドルがへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::Execute`します。  
  
 [!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [チュートリアル](../../atl/active-template-library-atl-tutorial.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
