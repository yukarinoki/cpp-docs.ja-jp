---
description: '詳細情報: CD2DMesh クラス'
title: CD2DMesh クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
ms.openlocfilehash: fbdb941d04b87df5c136f1925445564caab63443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193371"
---
# <a name="cd2dmesh-class"></a>CD2DMesh クラス

ID2D1Mesh のラッパー。

## <a name="syntax"></a>構文

```
class CD2DMesh : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DMesh:: CD2DMesh](#cd2dmesh)|CD2DMesh オブジェクトを構築します。|
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|デストラクターです。 D2D メッシュオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DMesh:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DMesh:: Create](#create)|CD2DMesh を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DMesh::D estroy](#destroy)|CD2DMesh オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DMesh::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DMesh:: Get](#get)|ID2D1Mesh インターフェイスを返します。|
|[CD2DMesh:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|
|[CD2DMesh:: Open](#open)|母集団のメッシュを開きます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DMesh:: operator ID2D1Mesh *](#operator_id2d1mesh_star)|ID2D1Mesh インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DMesh:: m_pMesh](#m_pmesh)|ID2D1Mesh へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a> CD2DMesh:: ~ CD2DMesh

デストラクターです。 D2D メッシュオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a> CD2DMesh:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a> CD2DMesh:: CD2DMesh

CD2DMesh オブジェクトを構築します。

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dmeshcreate"></a><a name="create"></a> CD2DMesh:: Create

CD2DMesh を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a> CD2DMesh::D estroy

CD2DMesh オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a> CD2DMesh::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dmeshget"></a><a name="get"></a> CD2DMesh:: Get

ID2D1Mesh インターフェイスを返します。

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Mesh インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a> CD2DMesh:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a> CD2DMesh:: m_pMesh

ID2D1Mesh へのポインター。

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a> CD2DMesh:: Open

母集団のメッシュを開きます。

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>戻り値

メッシュにデータを設定するために使用される ID2D1TessellationSink へのポインター。

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a> CD2DMesh:: operator ID2D1Mesh *

ID2D1Mesh インターフェイスを返します。

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>戻り値

ID2D1Mesh インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
