---
description: '詳細情報: CPictureHolder クラス'
title: CPictureHolder クラス
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: 47eacb66191e21b300aaa0d06bc23155fabaf651
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301478"
---
# <a name="cpictureholder-class"></a>CPictureHolder クラス

Picture プロパティを実装します。これにより、ユーザーがコントロールに画像を表示できるようになります。

## <a name="syntax"></a>構文

```
class CPictureHolder
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CPictureHolder:: CPictureHolder](#cpictureholder)|`CPictureHolder` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPictureHolder:: CreateEmpty](#createempty)|空の `CPictureHolder` オブジェクトを作成します。|
|[CPictureHolder:: CreateFromBitmap](#createfrombitmap)|`CPictureHolder`ビットマップからオブジェクトを作成します。|
|[CPictureHolder:: CreateFromIcon](#createfromicon)|`CPictureHolder`アイコンからオブジェクトを作成します。|
|[CPictureHolder:: CreateFromMetafile](#createfrommetafile)|`CPictureHolder`メタファイルからオブジェクトを作成します。|
|[CPictureHolder:: GetDisplayString](#getdisplaystring)|コントロールコンテナーのプロパティブラウザーに表示される文字列を取得します。|
|[CPictureHolder:: Getピクチャディスパッチ](#getpicturedispatch)|`CPictureHolder`オブジェクトのインターフェイスを返し `IDispatch` ます。|
|[CPictureHolder:: GetType](#gettype)|`CPictureHolder`オブジェクトがビットマップ、メタファイル、アイコンのいずれであるかを示します。|
|[CPictureHolder:: Render](#render)|画像をレンダリングします。|
|[CPictureHolder:: Setピクチャディスパッチ](#setpicturedispatch)|`CPictureHolder`オブジェクトのインターフェイスを設定し `IDispatch` ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPictureHolder:: m_pPict](#m_ppict)|ピクチャオブジェクトへのポインター。|

## <a name="remarks"></a>解説

`CPictureHolder` に基底クラスがありません。

ストック Picture プロパティを使用すると、開発者は表示するビットマップ、アイコン、またはメタファイルを指定できます。

カスタム picture プロパティの作成の詳細については、「 [MFC Activex コントロール: Activex コントロールでのピクチャの使用](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CPictureHolder`

## <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a> CPictureHolder:: CPictureHolder

`CPictureHolder` オブジェクトを構築します。

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a> CPictureHolder:: CreateEmpty

空 `CPictureHolder` のオブジェクトを作成し、インターフェイスに接続し `IPicture` ます。

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a> CPictureHolder:: CreateFromBitmap

ビットマップを使用して、のピクチャオブジェクトを初期化し `CPictureHolder` ます。

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>パラメーター

*idResource*<br/>
ビットマップリソースのリソース ID。

*pBitmap*<br/>
[CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトへのポインター。

*pPal*<br/>
[CPalette](../../mfc/reference/cpalette-class.md)オブジェクトへのポインター。

*bTransferOwnership 所有権*<br/>
Picture オブジェクトがビットマップオブジェクトとパレットオブジェクトの所有権を取得するかどうかを示します。

*hbm*<br/>
オブジェクトの作成元のビットマップを処理 `CPictureHolder` します。

*hpal*<br/>
ビットマップのレンダリングに使用されるパレットへのハンドル。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Btransferownership* が TRUE の場合、呼び出し元は、この呼び出しが返された後に、ビットマップまたはパレットオブジェクトを使用しないようにする必要があります。 *Btransferownership* が FALSE の場合、呼び出し元は、bitmap オブジェクトと palette オブジェクトが picture オブジェクトの有効期間にわたって有効であることを保証する役割を担います。

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a> CPictureHolder:: CreateFromIcon

アイコンを使用して、のピクチャオブジェクトを初期化し `CPictureHolder` ます。

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>パラメーター

*idResource*<br/>
ビットマップリソースのリソース ID。

*hIcon*<br/>
オブジェクトの作成元となるアイコンへのハンドル `CPictureHolder` 。

*bTransferOwnership 所有権*<br/>
Picture オブジェクトが icon オブジェクトの所有権を取得するかどうかを示します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Btransferownership 所有権* が TRUE の場合、呼び出し元は、この呼び出しが返された後に icon オブジェクトを使用しないようにする必要があります。 *Btransferownership* が FALSE の場合、呼び出し元は、icon オブジェクトが picture オブジェクトの有効期間にわたって有効であることを確認する役割を担います。

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a> CPictureHolder:: CreateFromMetafile

メタファイルを使用して、内の picture オブジェクトを初期化し `CPictureHolder` ます。

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>パラメーター

*hmf*<br/>
オブジェクトの作成に使用されたメタファイルへのハンドル `CPictureHolder` 。

*xExt*<br/>
画像の X 範囲。

*yExt*<br/>
画像の Y 範囲。

*bTransferOwnership 所有権*<br/>
Picture オブジェクトが metafile オブジェクトの所有権を取得するかどうかを示します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Btransferownership* が TRUE の場合、呼び出し元は、この呼び出しが返された後に、メタファイルオブジェクトを使用しないようにする必要があります。 *Btransferownership* が FALSE の場合、呼び出し元は、picture オブジェクトの有効期間中はメタファイルオブジェクトが有効であることを確認する役割を担います。

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a> CPictureHolder:: GetDisplayString

コンテナーのプロパティブラウザーに表示される文字列を取得します。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>パラメーター

*strValue*<br/>
表示文字列を保持する [CString](../../atl-mfc-shared/reference/cstringt-class.md) への参照。

### <a name="return-value"></a>戻り値

文字列が正常に取得された場合は0以外の値。それ以外の場合は0です。

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a> CPictureHolder:: Getピクチャディスパッチ

この関数は、オブジェクトのインターフェイスへのポインターを返し `CPictureHolder` `IPictureDisp` ます。

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>戻り値

`CPictureHolder`オブジェクトのインターフェイスへのポインター `IPictureDisp` 。

### <a name="remarks"></a>解説

呼び出し元は、 `Release` 終了時にこのポインターに対してを呼び出す必要があります。

## <a name="cpictureholdergettype"></a><a name="gettype"></a> CPictureHolder:: GetType

画像がビットマップ、メタファイル、アイコンのいずれであるかを示します。

```
short GetType();
```

### <a name="return-value"></a>戻り値

画像の種類を示す値です。 使用できる値とその意味は次のとおりです。

|値|説明|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` オブジェクトは unititialized です。|
|PICTYPE_NONE|`CPictureHolder` オブジェクトが空です。|
|PICTYPE_BITMAP|画像はビットマップです。|
|PICTYPE_METAFILE|Picture はメタファイルです。|
|PICTYPE_ICON|画像はアイコンです。|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a> CPictureHolder:: m_pPict

`CPictureHolder`オブジェクトのインターフェイスへのポインター `IPicture` 。

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a> CPictureHolder:: Render

*RcRender* によって参照される四角形に画像を表示します。

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
画像がレンダリングされる表示コンテキストへのポインター。

*rcRender*<br/>
画像を描画する四角形。

*rcWBounds*<br/>
画像を表示するオブジェクトの外接する四角形を表す四角形。 コントロールの場合、この四角形は、 [COleControl:: OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)のオーバーライドに渡される *rcbounds* パラメーターです。

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a> CPictureHolder:: Setピクチャディスパッチ

オブジェクトを `CPictureHolder` インターフェイスに接続し `IPictureDisp` ます。

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
新しいインターフェイスへのポインター `IPictureDisp` 。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder クラス](../../mfc/reference/cfontholder-class.md)
