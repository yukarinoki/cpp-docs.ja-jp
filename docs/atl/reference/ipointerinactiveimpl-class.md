---
title: IPointerInactiveImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: d7d9f048fceb3a569b024d7fe2b87f30a828b68e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274829"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl クラス

このクラスは実装`IUnknown`と[IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive)インターフェイスのメソッド。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPointerInactiveImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|オブジェクトの現在のアクティブ化ポリシーを取得します。 ATL の実装では、E_NOTIMPL を返します。|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることができますを通知します。 ATL の実装では、E_NOTIMPL を返します。|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|非アクティブなオブジェクトにマウス ポインターを設定します。 ATL の実装では、E_NOTIMPL を返します。|

## <a name="remarks"></a>Remarks

非アクティブなオブジェクトは、単に読み込まれたまたは実行中である 1 つです。 非アクティブなオブジェクトは、アクティブなオブジェクトとは異なり、Windows のマウスとキーボードのメッセージを受信できません。 したがって、非アクティブなオブジェクトは、使用リソースが少なくは通常より効率的です。

[IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive)インターフェイスが非アクティブなままマウスとの対話の最小レベルをサポートするためにオブジェクトを許可します。 この機能は、コントロールに特に便利です。

クラス`IPointerInactiveImpl`実装、 `IPointerInactive` E_NOTIMPL を単に返すことによってメソッド。 ただし、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy

オブジェクトの現在のアクティブ化ポリシーを取得します。

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IPointerInactive::GetActivationPolicy](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) Windows SDK にします。

##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove

マウス ポインターが上に移動されたオブジェクトを示すオブジェクトは、マウス イベントを発生させることができますを通知します。

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IPointerInactive::OnInactiveMouseMove](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) Windows SDK にします。

##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor

非アクティブなオブジェクトにマウス ポインターを設定します。

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IPointerInactive::OnInactiveSetCursor](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) Windows SDK にします。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
