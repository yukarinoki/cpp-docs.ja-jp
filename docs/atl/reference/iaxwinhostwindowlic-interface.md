---
title: IAxWinHostWindowLic インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: d7a63fc63b8abcf8574ea9a2fed2556635dba045
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352948"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic インターフェイス

このインターフェイスは、ライセンスされたコントロールとそのホストオブジェクトを操作するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[CreateControlLic](#createcontrollic)|ライセンスされたコントロールを作成し、ホストオブジェクトにアタッチします。|
|[CreateControlLicEx](#createcontrollicex)|ライセンスされたコントロールを作成し、ホストオブジェクトにアタッチし、必要に応じてイベントハンドラーを設定します。|

## <a name="remarks"></a>解説

`IAxWinHostWindowLic`[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)から継承し、ライセンスされたコントロールの作成をサポートするメソッドを追加します。

このインターフェイスのメンバーを使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次に示すように、IDL または C++ として使用できます。

|[定義の種類]|ファイル|
|---------------------|----------|
|IDL|ATLIFace|
|C++|ATLIFace (ATLBase. h にも含まれる)|

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> IAxWinHostWindowLic::CreateControlLic

ライセンスされたコントロールを作成して初期化し、で識別されるウィンドウでホストし `hWnd` ます。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
からコントロールのライセンスキーを格納している BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [IAxWinHostWindow:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) 」を参照してください。

このメソッドを呼び出すことは、 [IAxWinHostWindowLic:: CreateControlLicEx](#createcontrollicex)を呼び出すことと同じです。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください `IAxWinHostWindowLic::CreateControlLic` 。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> IAxWinHostWindowLic::CreateControlLicEx

ライセンスされた ActiveX コントロールを作成して初期化し、 [IAxWinHostWindow:: CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)と同様に、指定したウィンドウでホストします。

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
からコントロールのライセンスキーを格納している BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [IAxWinHostWindow:: CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください `IAxWinHostWindowLic::CreateControlLicEx` 。
