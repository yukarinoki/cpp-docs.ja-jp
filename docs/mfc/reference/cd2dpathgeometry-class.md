---
description: '詳細情報: CD2DPathGeometry クラス'
title: CD2DPathGeometry クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
ms.openlocfilehash: eb33d498436c887eb038b3312e2b98ca04d6620b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280535"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry クラス

ID2D1PathGeometry のラッパー。

## <a name="syntax"></a>構文

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DPathGeometry:: CD2DPathGeometry](#cd2dpathgeometry)|CD2DPathGeometry オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DPathGeometry:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DPathGeometry:: Create](#create)|CD2DPathGeometry を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DPathGeometry::D estroy](#destroy)|CD2DPathGeometry オブジェクトを破棄します。 ( [CD2DGeometry::D estroy](../../mfc/reference/cd2dgeometry-class.md#destroy)をオーバーライドします。)|
|[CD2DPathGeometry::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DPathGeometry:: GetFigureCount](#getfigurecount)|パスジオメトリ内の数値を取得します。|
|[CD2DPathGeometry:: GetSegmentCount](#getsegmentcount)|パスジオメトリ内のセグメントの数を取得します。|
|[CD2DPathGeometry:: Open](#open)|パスジオメトリに図形およびセグメントを設定するために使用されるジオメトリシンクを取得します。|
|[CD2DPathGeometry:: Stream](#stream)|パスジオメトリの内容を指定された ID2D1GeometrySink にコピーします。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DPathGeometry:: m_pPathGeometry](#m_ppathgeometry)|ID2D1PathGeometry へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a> CD2DPathGeometry:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a> CD2DPathGeometry:: CD2DPathGeometry

CD2DPathGeometry オブジェクトを構築します。

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a> CD2DPathGeometry:: Create

CD2DPathGeometry を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a> CD2DPathGeometry::D estroy

CD2DPathGeometry オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a> CD2DPathGeometry::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a> CD2DPathGeometry:: GetFigureCount

パスジオメトリ内の数値を取得します。

```
int GetFigureCount() const;
```

### <a name="return-value"></a>戻り値

パスジオメトリ内の図形の数を返します。

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a> CD2DPathGeometry:: GetSegmentCount

パスジオメトリ内のセグメントの数を取得します。

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>戻り値

パスジオメトリ内のセグメントの数を返します。

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a> CD2DPathGeometry:: m_pPathGeometry

ID2D1PathGeometry へのポインター。

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a> CD2DPathGeometry:: Open

パスジオメトリに図形およびセグメントを設定するために使用されるジオメトリシンクを取得します。

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>戻り値

パスジオメトリに図形とセグメントを設定するために使用される ID2D1GeometrySink へのポインター。

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a> CD2DPathGeometry:: Stream

パスジオメトリの内容を指定された ID2D1GeometrySink にコピーします。

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>パラメーター

*geometrySink*<br/>
パスジオメトリの内容のコピー先のシンク。 このシンクを変更しても、このパスジオメトリの内容は変更されません。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
