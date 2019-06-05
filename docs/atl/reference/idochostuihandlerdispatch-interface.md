---
title: IDocHostUIHandlerDispatch インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: f4f5024e282885797858c800640bc5651819ca20
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503067"
---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch インターフェイス

Microsoft の HTML 解析およびレンダリング エンジンへのインターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

> [!NOTE]
>  次の表のリンクがのメンバーの INet SDK リファレンスのトピックには、 [IDocUIHostHandler](/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))インターフェイス。 `IDocHostUIHandlerDispatch` 同じ機能を持つ`IDocUIHostHandler`、いるに違い`IDocHostUIHandlerDispatch`はディスパッチ インターフェイスに対し`IDocUIHostHandler`は、カスタム インターフェイスです。

|||
|-|-|
|[EnableModeless](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|MSHTML の実装から呼び出されます[IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)します。 MSHTML モーダル UI を表示するときとも呼ばれます。|
|[FilterDataObject](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|MSHTML のデータ オブジェクトを置換するホストを許可する MSHTML によってホストで呼び出されます。|
|[GetDropTarget](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|別の方法を指定するホストを許可する、ドロップ先として使用されている場合、MSHTML によって呼び出されます[IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)します。|
|[GetExternal](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|ホストの IDispatch インターフェイスを取得する MSHTML によって呼び出されます。|
|[GetHostInfo](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML ホストの UI 機能を取得します。|
|[GetOptionKeyPath](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML がユーザー設定を格納するレジストリ キーを返します。|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML がメニューやツールバーを削除するときに呼び出されます。|
|[OnDocWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|MSHTML の実装から呼び出されます[::ondocwindowactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)します。|
|[OnFrameWindowActivate](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|MSHTML の実装から呼び出されます[ioleinplaceactiveobject::onframewindowactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)します。|
|[ResizeBorder](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|MSHTML の実装から呼び出されます[ioleinplaceactiveobject:](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)します。|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|コンテキスト メニューを表示する MSHTML から呼び出されます。|
|[ShowUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|MSHTML メニューおよびツールバーを置換するホストを使用します。|
|[TranslateAccelerator](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|MSHTML によって呼び出されるときに[ioleinplaceactiveobject::translateaccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator)または[iolecontrolsite:](/windows/desktop/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator)が呼び出されます。|
|[TranslateUrl](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|ホストに読み込まれる URL を変更することを許可する MSHTML によって呼び出されます。|
|[Updateui という](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|コマンドの状態が変化したことをホストに通知します。|

## <a name="remarks"></a>Remarks

ホストは、メニューのツールバー、および Microsoft HTML 解析およびレンダリング エンジン (MSHTML) によってこのインターフェイスを実装するために使用するコンテキスト メニューに置き換えることができます。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次に示すように IDL または C++ では、使用可能です。

|定義の種類|ファイル|
|---------------------|----------|
|IDL|ATLIFace.idl|
|C++|ATLIFace.h (ATLBase.h にも含まれています)|

## <a name="see-also"></a>関連項目

[IDocUIHostHandler](/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
