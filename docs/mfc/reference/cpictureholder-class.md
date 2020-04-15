---
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
ms.openlocfilehash: 067ea7238c48f2698d7bfe469e9c4be10129c065
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364051"
---
# <a name="cpictureholder-class"></a>CPictureHolder クラス

ユーザーがコントロールにピクチャを表示できるようにする Picture プロパティを実装します。

## <a name="syntax"></a>構文

```
class CPictureHolder
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cピクチャーホルダー::Cピクチャーホルダー](#cpictureholder)|`CPictureHolder` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cピクチャーホルダー::空を作成します](#createempty)|空の `CPictureHolder` オブジェクトを作成します。|
|[をクリックします。](#createfrombitmap)|ビットマップから`CPictureHolder`オブジェクトを作成します。|
|[Cピクチャーホルダー::アイコンを作成します。](#createfromicon)|アイコンから`CPictureHolder`オブジェクトを作成します。|
|[C ピクチャーホルダー::メタファイルから作成します。](#createfrommetafile)|メタファイル`CPictureHolder`からオブジェクトを作成します。|
|[C ピクチャーホルダー::ゲットディスプレイ文字列](#getdisplaystring)|コントロール コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|
|[C ピクチャーホルダー::ゲットピクチャーディスパッチ](#getpicturedispatch)|オブジェクトの`CPictureHolder`インターフェイスを`IDispatch`返します。|
|[C ピクチャーホルダー::ゲットタイプ](#gettype)|オブジェクトが`CPictureHolder`ビットマップ、メタファイル、またはアイコンのいずれであるかを示します。|
|[Cピクチャーホルダー::レンダリング](#render)|画像をレンダリングします。|
|[C ピクチャーホルダー::セットピクチャーディスパッチ](#setpicturedispatch)|オブジェクトの`CPictureHolder`インターフェイスを`IDispatch`設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cピクチャーホルダー::m_pPict](#m_ppict)|ピクチャ オブジェクトへのポインター。|

## <a name="remarks"></a>解説

`CPictureHolder`は基本クラスを持っていません。

ストック ピクチャ プロパティを使用すると、表示するビットマップ、アイコン、またはメタファイルを指定できます。

カスタムピクチャプロパティの作成については[、「MFC ActiveX コントロール: ActiveX コントロールでのピクチャの使用](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CPictureHolder`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a>Cピクチャーホルダー::Cピクチャーホルダー

`CPictureHolder` オブジェクトを構築します。

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a>Cピクチャーホルダー::空を作成します

空`CPictureHolder`のオブジェクトを作成し、`IPicture`インターフェイスに接続します。

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a>をクリックします。

ビットマップを使用して、 のピクチャ オブジェクト`CPictureHolder`を初期化します。

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

*idリソース*<br/>
ビットマップ リソースのリソース ID。

*ビットマップ*<br/>
[オブジェクト](../../mfc/reference/cbitmap-class.md)へのポインター。

*pパル*<br/>
[CPalette](../../mfc/reference/cpalette-class.md)オブジェクトへのポインター。

*を使用します。*<br/>
ピクチャ オブジェクトがビットマップ オブジェクトとパレット オブジェクトの所有権を取得するかどうかを示します。

*Hbm*<br/>
オブジェクトの作成元のビットマップへの`CPictureHolder`ハンドル。

*hpal*<br/>
ビットマップのレンダリングに使用するパレットへのハンドル。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*bTransferOwnership*が TRUE の場合、呼び出し元は、この呼び出しが戻った後、ビットマップまたはパレット オブジェクトを使用しないでください。 *bTransferOwnership*が FALSE の場合、ビットマップとパレット オブジェクトがピクチャ オブジェクトの有効期間にわたって有効であることを確認する必要があります。

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a>Cピクチャーホルダー::アイコンを作成します。

アイコンを使用して、 のピクチャ オブジェクト`CPictureHolder`を初期化します。

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>パラメーター

*idリソース*<br/>
ビットマップ リソースのリソース ID。

*Hicon*<br/>
オブジェクトの作成元のアイコンへの`CPictureHolder`ハンドル。

*を使用します。*<br/>
ピクチャ オブジェクトがアイコン オブジェクトの所有権を取得するかどうかを示します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*bTransferOwnership*が TRUE の場合、呼び出し元は、この呼び出しが戻った後に、アイコン オブジェクトを使用しないでください。 *bTransferOwnership*が FALSE の場合、呼び出し元はアイコン オブジェクトがピクチャ オブジェクトの有効期間にわたって有効であることを確認する必要があります。

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a>C ピクチャーホルダー::メタファイルから作成します。

メタファイルを使用して、 のピクチャ オブジェクト`CPictureHolder`を初期化します。

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>パラメーター

*hmf*<br/>
オブジェクトの作成に使用するメタファイルへの`CPictureHolder`ハンドル。

*xExt*<br/>
画像の X 範囲。

*yExt*<br/>
画像の Y 範囲。

*を使用します。*<br/>
ピクチャ オブジェクトがメタファイル オブジェクトの所有権を取得するかどうかを示します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*bTransferOwnership*が TRUE の場合、呼び出し元は、この呼び出しが戻った後、メタファイル オブジェクトを使用しないでください。 *bTransferOwnership*が FALSE の場合、呼び出し元は、メタファイル オブジェクトがピクチャ オブジェクトの有効期間にわたって有効であることを確認する必要があります。

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a>C ピクチャーホルダー::ゲットディスプレイ文字列

コンテナーのプロパティ ブラウザーに表示される文字列を取得します。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>パラメーター

*strValue*<br/>
表示文字列を保持する[CString](../../atl-mfc-shared/reference/cstringt-class.md)への参照。

### <a name="return-value"></a>戻り値

文字列が正常に取得された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a>C ピクチャーホルダー::ゲットピクチャーディスパッチ

この関数は、オブジェクトの`CPictureHolder``IPictureDisp`インターフェイスへのポインターを返します。

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>戻り値

オブジェクトの`CPictureHolder``IPictureDisp`インターフェイスへのポインター。

### <a name="remarks"></a>解説

呼び出し`Release`元は、このポインターを呼び出す必要があります。

## <a name="cpictureholdergettype"></a><a name="gettype"></a>C ピクチャーホルダー::ゲットタイプ

画像がビットマップ、メタファイル、またはアイコンのいずれであるかを示します。

```
short GetType();
```

### <a name="return-value"></a>戻り値

画像の種類を示す値。 値とその意味は次のとおりです。

|[値]|意味|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder`オブジェクトは、ユニット化されます。|
|PICTYPE_NONE|`CPictureHolder`オブジェクトが空です。|
|PICTYPE_BITMAP|ピクチャはビットマップです。|
|PICTYPE_METAFILE|画像はメタファイルです。|
|PICTYPE_ICON|ピクチャはアイコンです。|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a>Cピクチャーホルダー::m_pPict

オブジェクトの`CPictureHolder``IPicture`インターフェイスへのポインター。

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a>Cピクチャーホルダー::レンダリング

*rcRender*によって参照される四角形にピクチャをレンダリングします。

```
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ピクチャが描画される表示コンテキストへのポインター。

*rcレンダリング*<br/>
ピクチャが描画される四角形。

*rcWバウンド*<br/>
ピクチャを描画するオブジェクトの外接する四角形を表す四角形。 コントロールの場合、この四角形は[COleControl::OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)のオーバーライドに渡される*rcBounds*パラメーターです。

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a>C ピクチャーホルダー::セットピクチャーディスパッチ

オブジェクトを`CPictureHolder`インターフェイスに`IPictureDisp`接続します。

```
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
新しい`IPictureDisp`インターフェイスへのポインター。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder クラス](../../mfc/reference/cfontholder-class.md)
