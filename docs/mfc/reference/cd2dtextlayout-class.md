---
title: CD2DTextLayout クラス
ms.date: 03/27/2019
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
helpviewer_keywords:
- CD2DTextLayout [MFC], CD2DTextLayout
- CD2DTextLayout [MFC], Create
- CD2DTextLayout [MFC], Destroy
- CD2DTextLayout [MFC], Get
- CD2DTextLayout [MFC], GetFontFamilyName
- CD2DTextLayout [MFC], GetLocaleName
- CD2DTextLayout [MFC], IsValid
- CD2DTextLayout [MFC], ReCreate
- CD2DTextLayout [MFC], SetFontFamilyName
- CD2DTextLayout [MFC], SetLocaleName
- CD2DTextLayout [MFC], m_pTextLayout
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
ms.openlocfilehash: 9be4c1134e2f82ceb3af31cbeb1a7d55f4071777
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369026"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout クラス

IDWriteText レイアウトのラッパー。

## <a name="syntax"></a>構文

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[テキストレイアウト::CD2D テキストレイアウト](#cd2dtextlayout)|オブジェクトを作成します。|
|[テキストレイアウト::~CD2D テキストレイアウト](#_dtorcd2dtextlayout)|デストラクターです。 D2D テキスト レイアウト オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2D テキストレイアウト::作成](#create)|を作成します。 [(CD2D リソースをオーバーライドします::作成](../../mfc/reference/cd2dresource-class.md#create).)|
|[CD2Dテキストレイアウト::Dエストロイ](#destroy)|オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[テキストレイアウト::取得します。](#get)|インターフェイスを返します。|
|[テキストレイアウト::フォントファミリ名](#getfontfamilyname)|指定した位置にあるテキストのフォント ファミリ名をコピーします。|
|[テキストレイアウト::ロケール名を取得します。](#getlocalename)|指定した位置にあるテキストのロケール名を取得します。|
|[テキストレイアウト::IsValid](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2D テキストレイアウト::再作成](#recreate)|CD2D テキストレイアウトを再作成します。 [(CD2D リソースをオーバーライドします::再作成](../../mfc/reference/cd2dresource-class.md#recreate).)|
|[テキストレイアウト::フォントファミリ名](#setfontfamilyname)|指定したテキスト範囲内のテキストに対して、NULL で終わるフォント ファミリ名を設定します。|
|[テキストレイアウト::セットロケール名](#setlocalename)|指定したテキスト範囲内のテキストのロケール名を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[テキストレイアウト::演算子 ID 書き込みテキストレイアウト*](#operator_idwritetextlayout_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2D テキストレイアウト::m_pTextLayout](#m_ptextlayout)|を指すポインターを配置します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

[テキストレイアウト](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a>テキストレイアウト::~CD2D テキストレイアウト

デストラクターです。 D2D テキスト レイアウト オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a>テキストレイアウト::CD2D テキストレイアウト

オブジェクトを作成します。

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*str テキスト*<br/>
新しい CD2DTextLayout オブジェクトを作成する文字列を含む CString オブジェクト。

*textFormat*<br/>
文字列に適用する書式を含む CString オブジェクト。

*サイズマックス*<br/>
レイアウト ボックスのサイズ。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a>CD2D テキストレイアウト::作成

を作成します。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a>CD2Dテキストレイアウト::Dエストロイ

オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a>テキストレイアウト::取得します。

インターフェイスを返します。

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、IDWriteTextLayout インターフェイスへのポインターまたは NULL。

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a>テキストレイアウト::フォントファミリ名

指定した位置にあるテキストのフォント ファミリ名をコピーします。

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>パラメーター

*現在の位置*<br/>
検査するテキストの位置。

*Textrange*<br/>
currentPosition で指定された位置にあるテキストと同じ書式を持つテキストの範囲。 つまり、実行は、フォント ファミリ名を含むがこれらに限定されない、指定された位置と完全に書式が設定されます。

### <a name="return-value"></a>戻り値

現在のフォント ファミリ名を含む CString オブジェクト。

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a>テキストレイアウト::ロケール名を取得します。

指定した位置にあるテキストのロケール名を取得します。

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>パラメーター

*現在の位置*<br/>
検査するテキストの位置。

*Textrange*<br/>
currentPosition で指定された位置にあるテキストと同じ書式を持つテキストの範囲。 つまり、実行は、ロケール名を含むがこれらに限定されない、指定された位置と完全に書式が設定されます。

### <a name="return-value"></a>戻り値

現在のロケール名を含む CString オブジェクト。

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a>テキストレイアウト::IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a>CD2D テキストレイアウト::m_pTextLayout

を指すポインターを配置します。

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a>テキストレイアウト::演算子 ID 書き込みテキストレイアウト*

インターフェイスを返します。

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>戻り値

オブジェクトがまだ初期化されていない場合は、IDWriteTextLayout インターフェイスへのポインターまたは NULL。

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a>CD2D テキストレイアウト::再作成

CD2D テキストレイアウトを再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a>テキストレイアウト::フォントファミリ名

指定したテキスト範囲内のテキストに対して、NULL で終わるフォント ファミリ名を設定します。

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>パラメーター

*家族名*<br/>
textRange で指定された範囲内のテキスト文字列全体に適用されるフォント ファミリ名

*Textrange*<br/>
この変更が適用されるテキスト範囲

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a>テキストレイアウト::セットロケール名

指定したテキスト範囲内のテキストのロケール名を設定します。

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
NULL で終わるロケール名文字列

*Textrange*<br/>
この変更が適用されるテキスト範囲

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
