---
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
ms.openlocfilehash: 5e747eda42e625d0f4cf65859e471933bbb043ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369095"
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
|[リソース::CD2Dリソース](#cd2dresource)|オブジェクトを作成します。|
|[リソース::~CD2Dリソース](#_dtorcd2dresource)|デストラクターです。 D2D リソース オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2D リソース::作成](#create)|CD2D リソースを作成します。|
|[CD2Dリソース::Dエストロイ](#destroy)|オブジェクトを破棄します。|
|[リソース::イズバリ](#isvalid)|リソースの有効性を確認します|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2D リソース::Is 自動破棄](#isautodestroy)|自動破壊フラグを確認してください。|
|[CD2D リソース::再作成](#recreate)|CD2D リソースを再作成します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[リソース:m_bIsAutoDestroy](#m_bisautodestroy)|リソースは所有者によって破棄されます (CRenderTarget)|
|[リソース:m_pParentTarget](#m_pparenttarget)|親のCRenderTargetへのポインタ)|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CD2DResource`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dresourcecd2dresource"></a><a name="_dtorcd2dresource"></a>リソース::~CD2Dリソース

デストラクターです。 D2D リソース オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DResource();
```

## <a name="cd2dresourcecd2dresource"></a><a name="cd2dresource"></a>リソース::CD2Dリソース

オブジェクトを作成します。

```
CD2DResource(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dresourcecreate"></a><a name="create"></a>CD2D リソース::作成

CD2D リソースを作成します。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dresourcedestroy"></a><a name="destroy"></a>CD2Dリソース::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy() = 0;
```

## <a name="cd2dresourceisautodestroy"></a><a name="isautodestroy"></a>CD2D リソース::Is 自動破棄

自動破壊フラグを確認してください。

```
BOOL IsAutoDestroy() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが所有者によって破棄される場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dresourceisvalid"></a><a name="isvalid"></a>リソース::イズバリ

リソースの有効性を確認します

```
virtual BOOL IsValid() const = 0;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dresourcem_bisautodestroy"></a><a name="m_bisautodestroy"></a>リソース:m_bIsAutoDestroy

リソースは所有者によって破棄されます (CRenderTarget)

```
BOOL m_bIsAutoDestroy;
```

## <a name="cd2dresourcem_pparenttarget"></a><a name="m_pparenttarget"></a>リソース:m_pParentTarget

親のCRenderTargetへのポインタ)

```
CRenderTarget* m_pParentTarget;
```

## <a name="cd2dresourcerecreate"></a><a name="recreate"></a>CD2D リソース::再作成

CD2D リソースを再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
レンダー ターゲットへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
