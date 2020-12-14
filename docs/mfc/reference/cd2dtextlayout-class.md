---
description: '詳細情報: CD2DTextLayout クラス'
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
ms.openlocfilehash: 164c8ed5561be6e8f9ee59b07d0aecaced5f7c81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240547"
---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout クラス

IDWriteTextLayout のラッパー。

## <a name="syntax"></a>構文

```
class CD2DTextLayout : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DTextLayout:: CD2DTextLayout](#cd2dtextlayout)|CD2DTextLayout オブジェクトを構築します。|
|[CD2DTextLayout:: ~ CD2DTextLayout](#_dtorcd2dtextlayout)|デストラクターです。 D2D テキストレイアウトオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DTextLayout:: Create](#create)|CD2DTextLayout を作成します。 ( [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create)をオーバーライドします)。|
|[CD2DTextLayout::D estroy](#destroy)|CD2DTextLayout オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DTextLayout:: Get](#get)|IDWriteTextLayout インターフェイスを返します|
|[CD2DTextLayout:: GetFontFamilyName](#getfontfamilyname)|指定した位置にあるテキストのフォントファミリ名をコピーします。|
|[CD2DTextLayout:: GetLocaleName](#getlocalename)|指定した位置にあるテキストのロケール名を取得します。|
|[CD2DTextLayout:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|
|[CD2DTextLayout:: 再作成](#recreate)|CD2DTextLayout を再作成します。 ( [CD2DResource:: 再作成](../../mfc/reference/cd2dresource-class.md#recreate)をオーバーライドします)。|
|[CD2DTextLayout:: SetFontFamilyName](#setfontfamilyname)|指定されたテキスト範囲内のテキストに対して、null で終わるフォントファミリ名を設定します。|
|[CD2DTextLayout:: SetLocaleName](#setlocalename)|指定したテキスト範囲内のテキストのロケール名を設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DTextLayout:: operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|IDWriteTextLayout インターフェイスを返します|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DTextLayout:: m_pTextLayout](#m_ptextlayout)|IDWriteTextLayout へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="_dtorcd2dtextlayout"></a> CD2DTextLayout:: ~ CD2DTextLayout

デストラクターです。 D2D テキストレイアウトオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DTextLayout();
```

## <a name="cd2dtextlayoutcd2dtextlayout"></a><a name="cd2dtextlayout"></a> CD2DTextLayout:: CD2DTextLayout

CD2DTextLayout オブジェクトを構築します。

```
CD2DTextLayout(
    CRenderTarget* pParentTarget,
    const CString& strText,
    CD2DTextFormat& textFormat,
    const CD2DSizeF& sizeMax,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*strText*<br/>
新しい CD2DTextLayout オブジェクトを作成する文字列を含む CString オブジェクト。

*textFormat*<br/>
文字列に適用する形式を格納している CString オブジェクト。

*sizeMax*<br/>
レイアウトボックスのサイズ。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dtextlayoutcreate"></a><a name="create"></a> CD2DTextLayout:: Create

CD2DTextLayout を作成します。

```
virtual HRESULT Create(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dtextlayoutdestroy"></a><a name="destroy"></a> CD2DTextLayout::D estroy

CD2DTextLayout オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dtextlayoutget"></a><a name="get"></a> CD2DTextLayout:: Get

IDWriteTextLayout インターフェイスを返します

```
IDWriteTextLayout* Get();
```

### <a name="return-value"></a>戻り値

IDWriteTextLayout インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dtextlayoutgetfontfamilyname"></a><a name="getfontfamilyname"></a> CD2DTextLayout:: GetFontFamilyName

指定した位置にあるテキストのフォントファミリ名をコピーします。

```
CString GetFontFamilyName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>パラメーター

*currentPosition*<br/>
確認するテキストの位置。

*textRange*<br/>
CurrentPosition によって指定された位置にあるテキストと同じ書式設定を持つテキストの範囲。 これは、指定された位置と同じ形式で実行されることを意味します。ただし、フォントファミリ名に限定されることはありません。

### <a name="return-value"></a>戻り値

現在のフォントファミリ名を格納している CString オブジェクト。

## <a name="cd2dtextlayoutgetlocalename"></a><a name="getlocalename"></a> CD2DTextLayout:: GetLocaleName

指定した位置にあるテキストのロケール名を取得します。

```
CString GetLocaleName(
    UINT32 currentPosition,
    DWRITE_TEXT_RANGE* textRange = NULL) const;
```

### <a name="parameters"></a>パラメーター

*currentPosition*<br/>
検査するテキストの位置。

*textRange*<br/>
CurrentPosition によって指定された位置にあるテキストと同じ書式設定を持つテキストの範囲。 つまり、実行は、指定された位置と同じ形式になりますが、ロケール名に限定されるわけではありません。

### <a name="return-value"></a>戻り値

現在のロケール名を含む CString オブジェクト。

## <a name="cd2dtextlayoutisvalid"></a><a name="isvalid"></a> CD2DTextLayout:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dtextlayoutm_ptextlayout"></a><a name="m_ptextlayout"></a> CD2DTextLayout:: m_pTextLayout

IDWriteTextLayout へのポインター。

```
IDWriteTextLayout* m_pTextLayout;
```

## <a name="cd2dtextlayoutoperator-idwritetextlayout"></a><a name="operator_idwritetextlayout_star"></a> CD2DTextLayout:: operator IDWriteTextLayout *

IDWriteTextLayout インターフェイスを返します

```
operator IDWriteTextLayout*();
```

### <a name="return-value"></a>戻り値

IDWriteTextLayout インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dtextlayoutrecreate"></a><a name="recreate"></a> CD2DTextLayout:: 再作成

CD2DTextLayout を再作成します。

```
virtual HRESULT ReCreate(CRenderTarget* */);
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラーコードを返します。

## <a name="cd2dtextlayoutsetfontfamilyname"></a><a name="setfontfamilyname"></a> CD2DTextLayout:: SetFontFamilyName

指定されたテキスト範囲内のテキストに対して、null で終わるフォントファミリ名を設定します。

```
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>パラメーター

*pwzFontFamilyName*<br/>
TextRange によって指定された範囲内のテキスト文字列全体に適用されるフォントファミリ名

*textRange*<br/>
この変更が適用されるテキスト範囲

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dtextlayoutsetlocalename"></a><a name="setlocalename"></a> CD2DTextLayout:: SetLocaleName

指定したテキスト範囲内のテキストのロケール名を設定します。

```
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,
    DWRITE_TEXT_RANGE textRange);
```

### <a name="parameters"></a>パラメーター

*pwzLocaleName*<br/>
Null で終わるロケール名の文字列

*textRange*<br/>
この変更が適用されるテキスト範囲

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
