---
description: '詳細情報: CD2DTextFormat クラス'
title: CD2DTextFormat クラス
ms.date: 03/27/2019
f1_keywords:
- CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::CD2DTextFormat
- AFXRENDERTARGET/CD2DTextFormat::Create
- AFXRENDERTARGET/CD2DTextFormat::Destroy
- AFXRENDERTARGET/CD2DTextFormat::Get
- AFXRENDERTARGET/CD2DTextFormat::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextFormat::GetLocaleName
- AFXRENDERTARGET/CD2DTextFormat::IsValid
- AFXRENDERTARGET/CD2DTextFormat::ReCreate
- AFXRENDERTARGET/CD2DTextFormat::m_pTextFormat
helpviewer_keywords:
- CD2DTextFormat [MFC], CD2DTextFormat
- CD2DTextFormat [MFC], Create
- CD2DTextFormat [MFC], Destroy
- CD2DTextFormat [MFC], Get
- CD2DTextFormat [MFC], GetFontFamilyName
- CD2DTextFormat [MFC], GetLocaleName
- CD2DTextFormat [MFC], IsValid
- CD2DTextFormat [MFC], ReCreate
- CD2DTextFormat [MFC], m_pTextFormat
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
ms.openlocfilehash: fc87aec6acb0e1eae0211555f1bdc943079081f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338326"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat クラス

IDWriteTextFormat のラッパー。

## <a name="syntax"></a>構文

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DTextFormat:: CD2DTextFormat](#cd2dtextformat)|CD2DTextFormat オブジェクトを構築します。|
|[CD2DTextFormat:: ~ CD2DTextFormat](#_dtorcd2dtextformat)|デストラクターです。 D2D テキスト形式のオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DTextFormat:: Create](#create)|CD2DTextFormat を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DTextFormat::D estroy](#destroy)|CD2DTextFormat オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DTextFormat:: Get](#get)|IDWriteTextFormat インターフェイスを返します|
|[CD2DTextFormat:: GetFontFamilyName](#getfontfamilyname)|フォントファミリ名のコピーを取得します。|
|[CD2DTextFormat:: GetLocaleName](#getlocalename)|ロケール名のコピーを取得します。|
|[CD2DTextFormat:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|
|[CD2DTextFormat:: 再作成](#recreate)|CD2DTextFormat を再作成します。 ( [CD2DResource:: 再作成](../../mfc/reference/cd2dresource-class.md#recreate)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DTextFormat:: operator IDWriteTextFormat *](#operator_idwritetextformat_star)|IDWriteTextFormat インターフェイスを返します|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DTextFormat:: m_pTextFormat](#m_ptextformat)|IDWriteTextFormat へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a> CD2DTextFormat:: ~ CD2DTextFormat

デストラクターです。 D2D テキスト形式のオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a> CD2DTextFormat:: CD2DTextFormat

CD2DTextFormat オブジェクトを構築します。

```
CD2DTextFormat(
    CRenderTarget* pParentTarget,
    const CString& strFontFamilyName,
    FLOAT fontSize,
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,
    const CString& strFontLocale = _T(""),
    IDWriteFontCollection* pFontCollection = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*strFontFamilyName*<br/>
フォントファミリの名前を格納している CString オブジェクト。

*fontSize*<br/>
DIP ("デバイス非依存ピクセル") 単位のフォントの論理サイズ。 DIPequals 1/96 インチ。

*fontWeight*<br/>
テキストオブジェクトのフォントの太さを示す値。

*fontStyle*<br/>
テキストオブジェクトのフォントスタイルを示す値。

*fontStretch*<br/>
テキストオブジェクトのフォント伸縮を示す値。

*strFontLocale*<br/>
ロケール名を格納している CString オブジェクト。

*pFontCollection*<br/>
フォントコレクションオブジェクトへのポインター。 NULL の場合、システムフォントのコレクションを示します。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dtextformatcreate"></a><a name="create"></a> CD2DTextFormat:: Create

CD2DTextFormat を作成します。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a> CD2DTextFormat::D estroy

CD2DTextFormat オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a> CD2DTextFormat:: Get

IDWriteTextFormat インターフェイスを返します

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>戻り値

IDWriteTextFormat インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextFormat:: GetFontFamilyName

フォントファミリ名のコピーを取得します。

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>戻り値

現在のフォントファミリ名を格納している CString オブジェクト。

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a> CD2DTextFormat:: GetLocaleName

ロケール名のコピーを取得します。

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>戻り値

現在のロケール名を含む CString オブジェクト。

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a> CD2DTextFormat:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a> CD2DTextFormat:: m_pTextFormat

IDWriteTextFormat へのポインター。

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a> CD2DTextFormat:: operator IDWriteTextFormat *

IDWriteTextFormat インターフェイスを返します

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>戻り値

IDWriteTextFormat インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a> CD2DTextFormat:: 再作成

CD2DTextFormat を再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
