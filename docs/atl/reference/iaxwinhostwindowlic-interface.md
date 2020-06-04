---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: 561a65702f1d4f57b4db1afc75769ce4cc523c1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329923"
---
# <a name="iaxwinhostwindowlic-interface"></a>インターフェイス

このインターフェイスは、ライセンスを受けたコントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[コントロールコントロールの作成](#createcontrollic)|ライセンスされたコントロールを作成し、ホスト オブジェクトにアタッチします。|
|[コントロールスライスを作成します。](#createcontrollicex)|ライセンスされたコントロールを作成し、ホスト オブジェクトに接続し、必要に応じてイベント ハンドラーを設定します。|

## <a name="remarks"></a>解説

`IAxWinHostWindowLic`[から](../../atl/reference/iaxwinhostwindow-interface.md)継承し、ライセンスを持つコントロールの作成をサポートするメソッドを追加します。

このインターフェイス[のメンバーを使用するサンプルについては、「ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md)」を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次に示すように、IDL または C++ として使用できます。

|[定義の種類]|ファイル|
|---------------------|----------|
|Idl|アトリフェイス.idl|
|C++|ATLIFace.h (ATLBase.h にも含まれています)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>をクリックします。

ライセンスされたコントロールを作成し、初期化し、 で`hWnd`識別されるウィンドウでホストします。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
[in]コントロールのライセンス キーを含む BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、IAxWinHostWindow::CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)を参照してください。

このメソッドを呼び出すことは、呼び出しと同等[です。](#createcontrollicex)

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`IAxWinHostWindowLic::CreateControlLic`してください。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>をクリックします。

ライセンスを受けた ActiveX コントロールを作成し、初期化し、指定されたウィンドウで[ホストします。](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
[in]コントロールのライセンス キーを含む BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、IAxWinHostWindow::CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`IAxWinHostWindowLic::CreateControlLicEx`してください。
