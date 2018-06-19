---
title: CAxWindow2T クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 077ecfe36e1ddf6c319f02bdabb89d660a5f22d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360759"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T クラス
このクラスは、ActiveX コントロールをホストし、ライセンスされた ActiveX コントロールをホストするためのサポートがウィンドウを操作するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>パラメーター  
 *TBase*  
 元のクラス`CAxWindowT`派生します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|`CAxWindow2T` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|ホスト ウィンドウを作成します。|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|ウィンドウ クラスの名前を取得する静的メソッド。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|割り当てます、`HWND`既存`CAxWindow2T`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CAxWindow2T` ActiveX コントロールをホストするウィンドウを操作するためのメソッドを提供します。 `CAxWindow2T` ライセンスされた ActiveX コントロールをホストするためのサポートがあります。 によって提供されるホスティング" **AtlAxWinLic80**"、によってラップされている`CAxWindow2T`です。  
  
 クラス`CAxWindow2`を特化したクラスとして実装されて、`CAxWindow2T`クラスです。 この特殊化は、としてを宣言されます。  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT` 下にあるメンバーが記載されている[CAxWindow](../../atl/reference/caxwindow-class.md)です。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)このクラスのメンバーを使用するサンプルについてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T  
 `CAxWindow2T` オブジェクトを構築します。  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウのハンドル。  
  
##  <a name="create"></a>  CAxWindow2T::Create  
 ホスト ウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>コメント  
 `CAxWindow2T::Create` 呼び出し[CWindow::Create](../../atl/reference/cwindow-class.md#create)で、`LPCTSTR lpstrWndClass`パラメーター コントロールのホスティングを提供する、ウィンドウ クラスに設定 ( **AtlAxWinLic80**)。  
  
 参照してください`CWindow::Create`パラメーターと戻り値の詳細についてはします。  
  
 **注**の値として 0 が使用する場合、`MenuOrID`パラメーターを 0 u として指定する必要があります (既定値)、コンパイラ エラーを回避します。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::Create`します。  
  
##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic  
 ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLicKey`  
 コントロールのライセンス キーライセンスの付いていないコントロールを作成する場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 参照してください[については](../../atl/reference/caxwindow-class.md#createcontrol)残りのパラメーターと戻り値の詳細についてはします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::CreateControlLic`します。  
  
##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx  
 ライセンスされた ActiveX コントロールを作成、初期化し、指定されたウィンドウでホストおよびコントロールからインターフェイス ポインター (またはポインター) を取得します。  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLicKey`  
 コントロールのライセンス キーライセンスの付いていないコントロールを作成する場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 参照してください[CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex)残りのパラメーターと戻り値の詳細についてはします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`CAxWindow2T::CreateControlLicEx`します。  
  
##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName  
 ウィンドウ クラスの名前を取得します。  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ クラスの名前を含む文字列へのポインター ( **AtlAxWinLic80**) ライセンスとライセンスの付いていない ActiveX コントロールをホストすることができます。  
  
##  <a name="operator_eq"></a>  CAxWindow2T::operator =  
 割り当てます、`HWND`既存`CAxWindow2T`オブジェクト。  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 既存のウィンドウのハンドル。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [コントロール コンテインメントよく寄せられる質問](../../atl/atl-control-containment-faq.md)
