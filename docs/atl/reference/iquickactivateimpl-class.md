---
title: IQuickActivateImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 96e165fcd4d38c9d263b48ee2c559394770a52a1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765721"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl クラス

このクラスは、1 つの呼び出しにコンテナーのコントロールの初期化を結合します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>パラメーター

*T*  
派生したクラス、`IQuickActivateImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|実行中のコントロールの現在の表示サイズを取得します。|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|読み込む対象のコントロールの初期化を迅速に実行します。|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|コンテナーに割り当てられている表示領域の量のコントロールに通知します。|

## <a name="remarks"></a>Remarks

[IQuickActivate](/windows/desktop/api/ocidl/nn-ocidl-iquickactivate)インターフェイス コンテナーは 1 回の呼び出しで初期化を組み合わせることでコントロールを読み込むときに遅延を避けるために役立ちます。 `QuickActivate`メソッドにより、コンテナーへのポインターを渡す、 [QACONTAINER](/windows/desktop/api/ocidl/ns-ocidl-tagqacontainer)構造、コントロールにすべてのインターフェイス ポインターを保持する必要があります。 返された場合、制御が渡されるバックアップへのポインターを[戻り値](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol)コンテナーで使用される、独自のインターフェイス ポインターを保持する構造体。 クラス`IQuickActivateImpl`の既定の実装を提供します。`IQuickActivate`実装と`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlctl.h

##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent

実行中のコントロールの現在の表示サイズを取得します。

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Remarks

サイズは、コントロールの完全なレンダリングは、HIMETRIC 単位で指定されます。

参照してください[IQuickActivate::GetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) Windows SDK にします。

##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate

読み込む対象のコントロールの初期化を迅速に実行します。

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Remarks

構造体には、コントロールと一部のアンビエント プロパティの値で必要なインターフェイスへのポインターが含まれています。 戻り時に、コントロールがへのポインターを渡す、[戻り値](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol)コンテナーが必要とする独自のインターフェイスと追加の状態情報へのポインターを含む構造体。

参照してください[IQuickActivate::QuickActivate](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-quickactivate) Windows SDK にします。

##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent

コンテナーに割り当てられている表示領域の量のコントロールに通知します。

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Remarks

サイズは、HIMETRIC 単位で指定されます。

参照してください[IQuickActivate::SetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) Windows SDK にします。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
