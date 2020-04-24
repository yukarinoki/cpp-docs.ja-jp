---
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
ms.openlocfilehash: eaecdb6ba6f1382f16177e0567b31c9fd09da6ff
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753094"
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
|[CD2Dメッシュ::CD2Dメッシュ](#cd2dmesh)|CD2D メッシュ オブジェクトを構築します。|
|[CD2Dメッシュ::〜CD2Dメッシュ](#_dtorcd2dmesh)|デストラクターです。 D2D メッシュ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dメッシュ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dメッシュ::作成](#create)|CD2D メッシュを作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dメッシュ::Dエストロイ](#destroy)|CD2D メッシュ オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2Dメッシュ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dメッシュ::取得](#get)|ID2D1メッシュインタフェースを返します|
|[CD2Dメッシュ::イズバリ](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2Dメッシュ::オープン](#open)|母集団のメッシュを開きます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dメッシュ::オペレーターID2D1メッシュ*](#operator_id2d1mesh_star)|ID2D1メッシュインタフェースを返します|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dメッシュ::m_pMesh](#m_pmesh)|ID2D1Mesh へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

`CD2DMesh`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dmeshcd2dmesh"></a><a name="_dtorcd2dmesh"></a>CD2Dメッシュ::〜CD2Dメッシュ

デストラクターです。 D2D メッシュ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DMesh();
```

## <a name="cd2dmeshattach"></a><a name="attach"></a>CD2Dメッシュ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Mesh* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dmeshcd2dmesh"></a><a name="cd2dmesh"></a>CD2Dメッシュ::CD2Dメッシュ

CD2D メッシュ オブジェクトを構築します。

```
CD2DMesh(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dmeshcreate"></a><a name="create"></a>CD2Dメッシュ::作成

CD2D メッシュを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dmeshdestroy"></a><a name="destroy"></a>CD2Dメッシュ::Dエストロイ

CD2D メッシュ オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dmeshdetach"></a><a name="detach"></a>CD2Dメッシュ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1Mesh* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dmeshget"></a><a name="get"></a>CD2Dメッシュ::取得

ID2D1メッシュインタフェースを返します

```
ID2D1Mesh* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Mesh インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dmeshisvalid"></a><a name="isvalid"></a>CD2Dメッシュ::イズバリ

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dmeshm_pmesh"></a><a name="m_pmesh"></a>CD2Dメッシュ::m_pMesh

ID2D1Mesh へのポインター。

```
ID2D1Mesh* m_pMesh;
```

## <a name="cd2dmeshopen"></a><a name="open"></a>CD2Dメッシュ::オープン

母集団のメッシュを開きます。

```
ID2D1TessellationSink* Open();
```

### <a name="return-value"></a>戻り値

メッシュの設定に使用される ID2D1TessellationSink へのポインター。

## <a name="cd2dmeshoperator-id2d1mesh"></a><a name="operator_id2d1mesh_star"></a>CD2Dメッシュ::オペレーターID2D1メッシュ*

ID2D1メッシュインタフェースを返します

```
operator ID2D1Mesh*();
```

### <a name="return-value"></a>戻り値

ID2D1Mesh インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
