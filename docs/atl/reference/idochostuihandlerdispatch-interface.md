---
title: インターフェイスをディスパッチします。
ms.date: 07/02/2019
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
ms.openlocfilehash: b7072b80b738aa12635427a2604b38fb3585b452
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329724"
---
# <a name="idochostuihandlerdispatch-interface"></a>インターフェイスをディスパッチします。

Microsoft HTML の解析およびレンダリング エンジンへのインターフェイス。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IDocHostUIHandlerDispatch : IDispatch
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

> [!NOTE]
> 次の表に示すリンクは[、IDocUIHostHandler](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))インターフェイスのメンバーの INet SDK リファレンス トピックへのリンクです。 `IDocHostUIHandlerDispatch`と同じ機能`IDocUIHostHandler`を持ち、異なるのは`IDocHostUIHandlerDispatch`、カスタム インターフェイスであるの`IDocUIHostHandler`に対し、その違いは、ディスインターフェイスです。

|||
|-|-|
|[モードレスを有効にする](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753253\(v=vs.85\))|の MSHTML 実装から呼び出[されます](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless)。 MSHTML がモーダル UI を表示するときにも呼び出されます。|
|[フィルターデータオブジェクト](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753254\(v=vs.85\))|MSHTML によってホストで呼び出され、ホストが MSHTML のデータ オブジェクトを置き換えることができます。|
|[ターゲットを取得します。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753255\(v=vs.85\))|ホストが代替[IDropTarget](/windows/win32/api/oleidl/nn-oleidl-idroptarget)を提供できるようにドロップ ターゲットとして使用されているときに MSHTML によって呼び出されます。|
|[外部を取得する](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753256\(v=vs.85\))|ホストの IDispatch インターフェイスを取得するために MSHTML によって呼び出されます。|
|[ホスト情報を取得します。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753257\(v=vs.85\))|MSHTML ホストの UI 機能を取得します。|
|[キーパスを取得します。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753258\(v=vs.85\))|MSHTML がユーザー設定を格納するレジストリ キーを返します。|
|[HideUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753259\(v=vs.85\))|MSHTML がメニューとツール バーを削除したときに呼び出されます。|
|[アクティブにします。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753261\(v=vs.85\))|の MSHTML 実装から呼び出[されます](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate)。|
|[オンフレームウィンドウアクティブ化](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753262\(v=vs.85\))|の MSHTML 実装から呼び出[されます](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate)。|
|[サイズ変更ボーダー](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753263\(v=vs.85\))|の MSHTML 実装から呼び出[されます](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder)。|
|[ShowContextMenu](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753264\(v=vs.85\))|コンテキスト メニューを表示するために MSHTML から呼び出されます。|
|[Showui](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753265\(v=vs.85\))|ホストが MSHTML メニューとツール バーを置き換えることを許可します。|
|[トランスレートアクセラレータ](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753266\(v=vs.85\))|ときに MSHTML によって呼び出[されます。](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) [IOleControlSite::TranslateAccelerator](/windows/win32/api/ocidl/nf-ocidl-iolecontrolsite-translateaccelerator)|
|[翻訳Url](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753267\(v=vs.85\))|ホストが読み込まれる URL を変更できるようにするために MSHTML によって呼び出されます。|
|[アップデートUI](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753268\(v=vs.85\))|コマンドの状態が変化したことをホストに通知します。|

## <a name="remarks"></a>解説

ホストは、このインターフェイスを実装することにより、Microsoft HTML 解析およびレンダリング エンジン (MSHTML) で使用されるメニュー、ツールバー、およびコンテキスト メニューを置き換えることができます。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次に示すように、IDL または C++ として使用できます。

|[定義の種類]|ファイル|
|---------------------|----------|
|Idl|アトリフェイス.idl|
|C++|ATLIFace.h (ATLBase.h にも含まれています)|

## <a name="see-also"></a>関連項目

[ホストハンドラー](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa753260\(v=vs.85\))
