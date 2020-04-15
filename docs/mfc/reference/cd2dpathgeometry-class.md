---
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
ms.openlocfilehash: 59ef82151983720b654502ccf3ca647e55366268
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369170"
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
|[ジオメトリ::CD2Dパスジオメトリ](#cd2dpathgeometry)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ジオメトリ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[ジオメトリ::作成](#create)|を作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[ジオメトリ::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2D ジオメトリ::Dエストロイ](../../mfc/reference/cd2dgeometry-class.md#destroy)をオーバーライドします。|
|[CD2Dパスジオメトリ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[ジオメトリ::ゲットフィギュアカウント](#getfigurecount)|パス ジオメトリ内の図形の数を取得します。|
|[ジオメトリ::セグメントカウントを取得します。](#getsegmentcount)|パス ジオメトリ内のセグメント数を取得します。|
|[ジオメトリ::オープン](#open)|パス ジオメトリに図形とセグメントを設定するために使用されるジオメトリ シンクを取得します。|
|[ソースのジオメトリ::ストリーム](#stream)|パス ジオメトリの内容を指定した ID2D1Geometry シンクにコピーします。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[ジオメトリ:m_pPathGeometry](#m_ppathgeometry)|ID2D1PathGeometry へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2Dジオメトリ](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a>ジオメトリ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a>ジオメトリ::CD2Dパスジオメトリ

オブジェクトを構築します。

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a>ジオメトリ::作成

を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a>ジオメトリ::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a>CD2Dパスジオメトリ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a>ジオメトリ::ゲットフィギュアカウント

パス ジオメトリ内の図形の数を取得します。

```
int GetFigureCount() const;
```

### <a name="return-value"></a>戻り値

パス ジオメトリ内の図形の数を返します。

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a>ジオメトリ::セグメントカウントを取得します。

パス ジオメトリ内のセグメント数を取得します。

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>戻り値

パス ジオメトリ内のセグメント数を返します。

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a>ジオメトリ:m_pPathGeometry

ID2D1PathGeometry へのポインター。

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a>ジオメトリ::オープン

パス ジオメトリに図形とセグメントを設定するために使用されるジオメトリ シンクを取得します。

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>戻り値

図形とセグメントを含むパス ジオメトリを設定するために使用される ID2D1GeometrySink へのポインター。

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a>ソースのジオメトリ::ストリーム

パス ジオメトリの内容を指定した ID2D1Geometry シンクにコピーします。

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>パラメーター

*ジオメトリシンク*<br/>
パス ジオメトリの内容のコピー先シンク。 このシンクを修正しても、このパス ジオメトリの内容は変更されません。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
