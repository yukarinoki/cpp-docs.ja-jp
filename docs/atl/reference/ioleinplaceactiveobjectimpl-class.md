---
description: '詳細情報: IOleInPlaceActiveObjectImpl クラス'
title: IOleInPlaceActiveObjectImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: 02f74e462dca2aac2749b8602281f40c8eacd0eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158193"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl クラス

このクラスは、インプレースコントロールとそのコンテナーとの間の通信を支援するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IOleInPlaceActiveObjectImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL 実装は E_NOTIMPL を返します。|
|[IOleInPlaceActiveObjectImpl:: EnableModeless](#enablemodeless)|モードレスダイアログボックスを有効にします。 ATL 実装は S_OK を返します。|
|[IOleInPlaceActiveObjectImpl:: GetWindow](#getwindow)|ウィンドウハンドルを取得します。|
|[IOleInPlaceActiveObjectImpl:: OnDocWindowActivate](#ondocwindowactivate)|コンテナーのドキュメントウィンドウがアクティブ化または非アクティブ化されたときに、コントロールに通知します。 ATL 実装は S_OK を返します。|
|[IOleInPlaceActiveObjectImpl:: OnFrameWindowActivate](#onframewindowactivate)|コンテナーの最上位レベルのフレームウィンドウがアクティブ化または非アクティブ化されたときに、コントロールに通知します。 ATL の実装はを返します。|
|[IOleInPlaceActiveObjectImpl:: ResizeBorder](#resizeborder)|境界線のサイズを変更する必要があることをコントロールに通知します。 ATL 実装は S_OK を返します。|
|[IOleInPlaceActiveObjectImpl:: TranslateAccelerator](#translateaccelerator)|コンテナーからのメニューアクセラレータキーメッセージを処理します。 ATL 実装は E_NOTIMPL を返します。|

## <a name="remarks"></a>解説

[IOleInPlaceActiveObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject)インターフェイスは、インプレースコントロールとそのコンテナーとの間の通信を支援します。たとえば、コントロールとコンテナーのアクティブな状態を通信し、そのコントロール自体のサイズを変更する必要があることをコントロールに通知します。 クラス `IOleInPlaceActiveObjectImpl` は、の既定の実装を提供 `IOleInPlaceActiveObject` し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってをサポートします。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a> IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

状況依存のヘルプを有効にします。

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleWindow:: ContextSensitiveHelp](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) 」を参照してください。

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a> IOleInPlaceActiveObjectImpl:: EnableModeless

モードレスダイアログボックスを有効にします。

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleInPlaceActiveObject:: EnableModeless](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) 」を参照してください。

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a> IOleInPlaceActiveObjectImpl:: GetWindow

コンテナーは、この関数を呼び出して、コントロールのウィンドウハンドルを取得します。

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>解説

現在ウィンドウに表示されている場合でも、一部のコンテナーはウィンドウなしで動作しません。 ATL の実装で `CComControl::m_bWasOnceWindowless` は、データメンバーが TRUE の場合、関数は E_FAIL を返します。 それ以外の場合、 \* *PHWND* が NULL でない場合、は `GetWindow` *phwnd* をコントロールクラスのデータメンバーに割り当て、 `m_hWnd` S_OK を返します。

Windows SDK の「 [IOleWindow:: GetWindow](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow) 」を参照してください。

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a> IOleInPlaceActiveObjectImpl:: OnDocWindowActivate

コンテナーのドキュメントウィンドウがアクティブ化または非アクティブ化されたときに、コントロールに通知します。

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleInPlaceActiveObject:: OnDocWindowActivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) 」を参照してください。

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a> IOleInPlaceActiveObjectImpl:: OnFrameWindowActivate

コンテナーの最上位レベルのフレームウィンドウがアクティブ化または非アクティブ化されたときに、コントロールに通知します。

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleInPlaceActiveObject:: Onフレーム Windowactivate](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) 」を参照してください。

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a> IOleInPlaceActiveObjectImpl:: ResizeBorder

境界線のサイズを変更する必要があることをコントロールに通知します。

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleInPlaceActiveObject:: ResizeBorder](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) 」を参照してください。

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a> IOleInPlaceActiveObjectImpl:: TranslateAccelerator

コンテナーからのメニューアクセラレータキーメッセージを処理します。

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>戻り値

このメソッドは、次の戻り値をサポートします。

メッセージが正常に変換されたかどうかを S_OK します。

メッセージが変換されなかった場合は S_FALSE します。

### <a name="remarks"></a>解説

Windows SDK の「 [IOleInPlaceActiveObject:: TranslateAccelerator](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) 」を参照してください。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロールインターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
