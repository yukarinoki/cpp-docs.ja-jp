---
title: クラスをクイックアクティブ化
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
ms.openlocfilehash: 7e1984249caf66e2986341f9c9f7a939d7039125
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329550"
---
# <a name="iquickactivateimpl-class"></a>クラスをクイックアクティブ化

このクラスは、コンテナーのコントロール初期化を 1 つの呼び出しに結合します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IQuickActivateImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[I クイックアクティブインプル::取得コンテンツエクステント](#getcontentextent)|実行中のコントロールの現在の表示サイズを取得します。|
|[Iクイックアクティブインプル::クイックアクティブ化](#quickactivate)|読み込まれるコントロールの迅速な初期化を実行します。|
|[I クイックアクティブインプル::セットコンテンツエクステント](#setcontentextent)|コンテナが割り当てた表示スペースの量をコントロールに通知します。|

## <a name="remarks"></a>解説

[IQuickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate)インターフェイスを使用すると、1 回の呼び出しで初期化を組み合わせることによって、コントロールを読み込むときの遅延を避けるためのコンテナーを使用できます。 この`QuickActivate`メソッドを使用すると、コンテナーは、コントロールに必要なすべてのインターフェイスへのポインターを保持する[QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer)構造体へのポインターを渡すことができます。 戻り値を返す際、コントロールは、コンテナーが使用する独自のインターフェイスへのポインターを保持する[QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol)構造体へのポインターを戻します。 クラス`IQuickActivateImpl`は、デバッグ ビルド`IQuickActivate`でダンプ`IUnknown`デバイスに情報を送信することにより、既定の実装と実装を提供します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>I クイックアクティブインプル::取得コンテンツエクステント

実行中のコントロールの現在の表示サイズを取得します。

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>解説

サイズはコントロールの完全なレンダリング用で、HIMETRIC 単位で指定されます。

Windows SDK[の「I クイックアクティベート::コンテンツエクステント](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent)」を参照してください。

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a>Iクイックアクティブインプル::クイックアクティブ化

読み込まれるコントロールの迅速な初期化を実行します。

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>解説

構造体には、コントロールが必要とするインターフェイスへのポインターと、いくつかのアンビエント プロパティの値が含まれています。 制御は、戻るときに、コンテナーが必要とする独自のインターフェースへのポインターと追加の状況情報を含む[QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol)構造体へのポインターを渡します。

「Windows SDK[で I クイックアクティブ化::クイックアクティブ化](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate)」を参照してください。

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>I クイックアクティブインプル::セットコンテンツエクステント

コンテナが割り当てた表示スペースの量をコントロールに通知します。

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>解説

サイズは HIMETRIC 単位で指定されます。

Windows SDK の[「I クイックアクティブ化::コンテンツエクステント](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent)」を参照してください。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
