---
description: '詳細情報: CD2DResource クラス'
title: CD2DResource クラス
ms.date: 03/27/2019
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
ms.openlocfilehash: a110732a7e2bde5ab2fb3b6025acf98d6a3278c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118733"
---
# <a name="cd2dresource-class"></a>CD2DResource クラス

ブラシ、レイヤー、テキストなどの D2D リソースを作成および管理するためのインターフェイスを提供する抽象クラス。

## <a name="syntax"></a>構文

```
class CD2DResource : public CObject;
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DResource:: CD2DResource](#cd2dresource)|CD2DResource オブジェクトを構築します。|
|[CD2DResource:: ~ CD2DResource](#_dtorcd2dresource)|デストラクターです。 D2D リソースオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DResource:: Create](#create)|CD2DResource を作成します。|
|[CD2DResource::D estroy](#destroy)|CD2DResource オブジェクトを破棄します。|
|[CD2DResource:: IsValid](#isvalid)|リソースの有効性を確認します|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2DResource:: IsAutoDestroy](#isautodestroy)|自動破棄フラグをオンにします。|
|[CD2DResource:: 再作成](#recreate)|CD2DResource を再作成します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DResource:: m_bIsAutoDestroy](#m_bisautodestroy)|リソースは所有者 (CRenderTarget) によって破棄されます|
|[CD2DResource:: m_pParentTarget](#m_pparenttarget)|親 CRenderTarget へのポインター|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a> CD2DResource:: ~ CD2DResource

デストラクターです。 D2D リソースオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a> CD2DResource:: CD2DResource

CD2DResource オブジェクトを構築します。

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dresourcecreate"></a><a name="create"></a> CD2DResource:: Create

CD2DResource を作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a> CD2DResource::D estroy

CD2DResource オブジェクトを破棄します。

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a> CD2DResource:: IsAutoDestroy

自動破棄フラグをオンにします。

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが所有者によって破棄される場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a> CD2DResource:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a> CD2DResource:: m_bIsAutoDestroy

リソースは所有者 (CRenderTarget) によって破棄されます

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a> CD2DResource:: m_pParentTarget

親 CRenderTarget へのポインター

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a> CD2DResource:: 再作成

CD2DResource を再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*pRenderTarget*<br/>
レンダーターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
