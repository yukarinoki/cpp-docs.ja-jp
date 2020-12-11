---
description: '詳細情報: Iquickの Impl クラス'
title: Iquickの Impl クラス
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 1e9dc2891351512ec3ebe54ebe6711ee9d4a3fa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158128"
---
# <a name="iquickactivateimpl-class"></a>Iquickの Impl クラス

このクラスは、コンテナーのコントロールの初期化を1回の呼び出しに結合します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IQuickActivateImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iquickの Impl:: GetContentExtent](#getcontentextent)|実行中のコントロールの現在の表示サイズを取得します。|
|[Iquickactivate Impl:: QuickActivate](#quickactivate)|読み込まれるコントロールのクイック初期化を実行します。|
|[Iquickの Impl:: SetContentExtent](#setcontentextent)|コンテナーに割り当てられている表示領域の大きさをコントロールに通知します。|

## <a name="remarks"></a>解説

[Iquickactivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate)インターフェイスを使用すると、1回の呼び出しで初期化を組み合わせることによって、コントロールを読み込むときの遅延を回避できます。 `QuickActivate`メソッドを使用すると、コンテナーは、コントロールが必要とするすべてのインターフェイスへのポインターを保持する[QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer)構造体へのポインターを渡すことができます。 制御が戻ったとき、コントロールは、コンテナーによって使用される独自のインターフェイスへのポインターを保持する [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) の構造体へのポインターを渡します。 クラス `IQuickActivateImpl` は、の既定の実装を提供 `IQuickActivate` し、 `IUnknown` デバッグビルドでダンプデバイスに情報を送信することによってを実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl. h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a> Iquickの Impl:: GetContentExtent

実行中のコントロールの現在の表示サイズを取得します。

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>解説

このサイズは、コントロールを完全にレンダリングするためのものであり、HIMETRIC 単位で指定されています。

Windows SDK の「 [Iquickactivate:: GetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) 」を参照してください。

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a> Iquickactivate Impl:: QuickActivate

読み込まれるコントロールのクイック初期化を実行します。

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>解説

構造体には、コントロールが必要とするインターフェイスへのポインターと、一部のアンビエントプロパティの値が含まれます。 制御が戻ったとき、コントロールは、コンテナーが必要とする独自のインターフェイスへのポインターと追加のステータス情報を含む [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) 構造体へのポインターを渡します。

Windows SDK の「 [Iquickactivate:: QuickActivate](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) 」を参照してください。

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a> Iquickの Impl:: SetContentExtent

コンテナーに割り当てられている表示領域の大きさをコントロールに通知します。

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>解説

サイズは、HIMETRIC 単位で指定します。

Windows SDK の「 [Iquickactivate:: SetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) 」を参照してください。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
