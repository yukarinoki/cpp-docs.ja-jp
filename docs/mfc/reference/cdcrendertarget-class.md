---
title: CDCRenderTarget クラス
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 790ce0f32c2325fa0ea92ca0bda64ddaa4c86c45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375703"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget クラス

ID2D1DCRenderターゲットのラッパー。

## <a name="syntax"></a>構文

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ターゲットを指定します。](#cdcrendertarget)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#attach)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|
|[を選択します。](#binddc)|描画コマンドを発行するデバイス コンテキストにレンダー ターゲットをバインドします。|
|[を選択します。](#create)|を作成します。|
|[CDCレンダーターゲット::Dエタッハ](#detach)|オブジェクトからレンダー ターゲット インターフェイスをデタッチします。|
|[をクリックします。](#getdcrendertarget)|インターフェイスを返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[を選択します。](#operator_id2d1dcrendertarget_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[m_pDCRenderTarget](#m_pdcrendertarget)|オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[クレンダターゲット](../../mfc/reference/crendertarget-class.md)

[ターゲット](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cdcrendertargetattach"></a><a name="attach"></a>をクリックします。

既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>パラメーター

*pターゲット*<br/>
既存のレンダー ターゲット インターフェイス。 NULL にすることはできません。

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a>を選択します。

描画コマンドを発行するデバイス コンテキストにレンダー ターゲットをバインドします。

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
レンダー ターゲットが描画コマンドを発行するデバイス コンテキスト

*Rect*<br/>
レンダー ターゲットがバインドされているデバイス コンテキスト (HDC) へのハンドルのサイズ

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a>ターゲットを指定します。

オブジェクトを構築します。

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a>を選択します。

を作成します。

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>パラメーター

*小道具*<br/>
レンダリング モード、ピクセル形式、リモート処理オプション、DPI 情報、およびハードウェア レンダリングに必要な最小 DirectX サポート。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cdcrendertargetdetach"></a><a name="detach"></a>CDCレンダーターゲット::Dエタッハ

オブジェクトからレンダー ターゲット インターフェイスをデタッチします。

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダー ターゲット インターフェイスへのポインター。

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a>をクリックします。

インターフェイスを返します。

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1DCRenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a>m_pDCRenderTarget

オブジェクトへのポインター。

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a>を選択します。

インターフェイスを返します。

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1DCRenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
