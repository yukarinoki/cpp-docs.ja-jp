---
title: クラスを挿入します。
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
ms.openlocfilehash: b39ba2845a5483444dac53d1616654e902969c77
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326584"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>クラスを挿入します。

このクラスは、インプレース コントロールとそのコンテナー間の通信を支援するメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IOleInPlaceActiveObjectImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コンテキスト依存ヘルプ::コンテキストインプレイスアクティブオブジェクトインプル::コンテキストヘルプ](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装はE_NOTIMPL返します。|
|[オブジェクトのインプル::モードレスを有効にします。](#enablemodeless)|モードレス ダイアログ ボックスを有効にします。 ATL 実装はS_OKを返します。|
|[オブジェクトのインプル::ウィンドウを取得します。](#getwindow)|ウィンドウ ハンドルを取得します。|
|[オブジェクトの挿入を行います。](#ondocwindowactivate)|コンテナーのドキュメント ウィンドウがアクティブまたは非アクティブになったときに、コントロールに通知します。 ATL 実装はS_OKを返します。|
|[アクティブ オブジェクトのインプル::オンフレーム ウィンドウアクティブ化](#onframewindowactivate)|コンテナーの最上位フレーム ウィンドウがアクティブまたは非アクティブになったときに、コントロールに通知します。 ATL 実装が返す|
|[オブジェクトのインプル::サイズ変更ボーダー](#resizeborder)|境界線のサイズを変更する必要があることをコントロールに通知します。 ATL 実装はS_OKを返します。|
|[オブジェクトのインプル::変換アクセラレータ](#translateaccelerator)|コンテナーからのメニュー アクセラレータ キー メッセージを処理します。 ATL の実装はE_NOTIMPL返します。|

## <a name="remarks"></a>解説

インターフェイス[は](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceactiveobject)、インプレース コントロールとそのコンテナー間の通信を支援します。たとえば、コントロールとコンテナーのアクティブ状態を通信し、サイズ変更が必要であることをコントロールに通知します。 クラス`IOleInPlaceActiveObjectImpl`は、デバッグ ビルド`IOleInPlaceActiveObject`でダンプ`IUnknown`デバイスに情報を送信することで、既定の実装とサポートを提供します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ioleinplaceactiveobjectimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>コンテキスト依存ヘルプ::コンテキストインプレイスアクティブオブジェクトインプル::コンテキストヘルプ

状況依存のヘルプを有効にします。

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOle ウィンドウ::コンテキストセンシティブヘルプ](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp)」を参照してください。

## <a name="ioleinplaceactiveobjectimplenablemodeless"></a><a name="enablemodeless"></a>オブジェクトのインプル::モードレスを有効にします。

モードレス ダイアログ ボックスを有効にします。

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[で「モードレスを有効にする」](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)を参照してください。

## <a name="ioleinplaceactiveobjectimplgetwindow"></a><a name="getwindow"></a>オブジェクトのインプル::ウィンドウを取得します。

コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>解説

一部のコンテナーは、ウィンドウがウィンドウに設定されている場合でも、ウィンドウなしのコントロールでは動作しません。 ATL の実装では、データ`CComControl::m_bWasOnceWindowless`メンバーが TRUE の場合、関数はE_FAIL返します。 それ以外の場合は\**、phwnd* `GetWindow`が NULL でない場合 *、phwnd*をコントロール`m_hWnd`クラスのデータ メンバーに割り当て、S_OK返します。

Windows SDK[の「IOle ウィンドウ::ウィンドウを取得](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow)する」を参照してください。

## <a name="ioleinplaceactiveobjectimplondocwindowactivate"></a><a name="ondocwindowactivate"></a>オブジェクトの挿入を行います。

コンテナーのドキュメント ウィンドウがアクティブまたは非アクティブになったときに、コントロールに通知します。

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

を[参照してください](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)。

## <a name="ioleinplaceactiveobjectimplonframewindowactivate"></a><a name="onframewindowactivate"></a>アクティブ オブジェクトのインプル::オンフレーム ウィンドウアクティブ化

コンテナーの最上位フレーム ウィンドウがアクティブまたは非アクティブになったときに、コントロールに通知します。

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

「ウィンドウ SDK[でアクティブ化する」](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)を参照してください。

## <a name="ioleinplaceactiveobjectimplresizeborder"></a><a name="resizeborder"></a>オブジェクトのインプル::サイズ変更ボーダー

境界線のサイズを変更する必要があることをコントロールに通知します。

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

Windows SDK[の「IOleInPlace アクティブオブジェクト::サイズ変更ボーダー](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) 」を参照してください。

## <a name="ioleinplaceactiveobjectimpltranslateaccelerator"></a><a name="translateaccelerator"></a>オブジェクトのインプル::変換アクセラレータ

コンテナーからのメニュー アクセラレータ キー メッセージを処理します。

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>戻り値

このメソッドは、次の戻り値をサポートします。

メッセージが正常に変換された場合にS_OKします。

メッセージが翻訳されなかった場合にS_FALSEします。

### <a name="remarks"></a>解説

Windows SDK[の「IOleInPlace アクティブオブジェクト::変換アクセラレータ](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator)」を参照してください。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX コントロール インターフェイス](/windows/win32/com/activex-controls-interfaces)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
