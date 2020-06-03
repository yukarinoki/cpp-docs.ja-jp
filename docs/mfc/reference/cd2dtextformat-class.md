---
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
ms.openlocfilehash: f7310fd3ca2ac34df7cc1a99cd5527ea8ba709c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369047"
---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat クラス

テキスト形式のラッパー。

## <a name="syntax"></a>構文

```
class CD2DTextFormat : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2D テキスト形式::CD2D テキスト形式](#cd2dtextformat)|オブジェクトを作成します。|
|[CD2D テキスト形式:~CD2D テキスト形式](#_dtorcd2dtextformat)|デストラクターです。 D2D テキスト形式オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2D テキスト形式::作成](#create)|CD2D テキスト形式を作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dテキストフォーマット::Dストロイ](#destroy)|オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2D テキストフォーマット::取得します。](#get)|インターフェイスを返します。|
|[テキスト形式::フォントファミリ名](#getfontfamilyname)|フォント ファミリ名のコピーを取得します。|
|[テキスト形式::ロケール名を取得します。](#getlocalename)|ロケール名のコピーを取得します。|
|[CD2D テキストフォーマット::IsValid](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2D テキスト形式::再作成](#recreate)|CD2D テキスト形式を再作成します。 [(CD2D リソースをオーバーライドします::再作成](../../mfc/reference/cd2dresource-class.md#recreate).)|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[テキスト形式::演算子 ID 書き込みテキスト形式*](#operator_idwritetextformat_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2D テキスト形式::m_pTextFormat](#m_ptextformat)|テキスト形式へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[CD2D テキスト形式](../../mfc/reference/cd2dtextformat-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2D テキスト形式:~CD2D テキスト形式

デストラクターです。 D2D テキスト形式オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DTextFormat();
```

## <a name="cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2D テキスト形式::CD2D テキスト形式

オブジェクトを作成します。

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

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*ストルフォントファミリ名*<br/>
フォント ファミリの名前を含む CString オブジェクト。

*Fontsize*<br/>
DIP ("デバイスに依存しないピクセル") 単位のフォントの論理サイズ。 DIPは1/96インチに等しい。

*Fontweight*<br/>
テキスト オブジェクトのフォントの太さを示す値。

*Fontstyle*<br/>
テキスト オブジェクトのフォント スタイルを示す値。

*フォントストレッチ*<br/>
テキスト オブジェクトのフォント伸縮を示す値。

*文字列の種類*<br/>
ロケール名を含む CString オブジェクト。

*フォントコレクション*<br/>
フォント コレクション オブジェクトへのポインター。 NULL の場合は、システム フォント コレクションを示します。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dtextformatcreate"></a><a name="create"></a>CD2D テキスト形式::作成

CD2D テキスト形式を作成します。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dtextformatdestroy"></a><a name="destroy"></a>CD2Dテキストフォーマット::Dストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dtextformatget"></a><a name="get"></a>CD2D テキストフォーマット::取得します。

インターフェイスを返します。

```
IDWriteTextFormat* Get();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、IDWriteTextFormat インターフェイスへのポインターまたは NULL。

## <a name="cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>テキスト形式::フォントファミリ名

フォント ファミリ名のコピーを取得します。

```
CString GetFontFamilyName() const;
```

### <a name="return-value"></a>戻り値

現在のフォント ファミリ名を含む CString オブジェクト。

## <a name="cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>テキスト形式::ロケール名を取得します。

ロケール名のコピーを取得します。

```
CString GetLocaleName() const;
```

### <a name="return-value"></a>戻り値

現在のロケール名を含む CString オブジェクト。

## <a name="cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2D テキストフォーマット::IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dtextformatm_ptextformat"></a><a name="m_ptextformat"></a>CD2D テキスト形式::m_pTextFormat

テキスト形式へのポインター。

```
IDWriteTextFormat* m_pTextFormat;
```

## <a name="cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>テキスト形式::演算子 ID 書き込みテキスト形式*

インターフェイスを返します。

```
operator IDWriteTextFormat*();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、IDWriteTextFormat インターフェイスへのポインターまたは NULL。

## <a name="cd2dtextformatrecreate"></a><a name="recreate"></a>CD2D テキスト形式::再作成

CD2D テキスト形式を再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
