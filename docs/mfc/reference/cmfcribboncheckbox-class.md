---
title: CMFCRibbonCheckBox クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
ms.openlocfilehash: a8048f860a2cce75c37a065cfdd2751141054f1b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446232"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox クラス

`CMFCRibbonCheckBox` クラスは、リボン パネル、クイック アクセス ツール バー、またはポップアップ メニューに追加できるチェック ボックスを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CMFCRibbonCheckBox:: GetCompactSize](#getcompactsize)|( [CMFCRibbonButton:: GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize)をオーバーライドします。)|
|[CMFCRibbonCheckBox:: GetIntermediateSize](#getintermediatesize)|( [CMFCRibbonButton:: GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize)をオーバーライドします。)|
|[CMFCRibbonCheckBox:: GetRegularSize](#getregularsize)|( [CMFCRibbonButton:: GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize)をオーバーライドします。)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(`CMFCRibbonButton::IsDrawTooltipImage` をオーバーライドします。)|
|[CMFCRibbonCheckBox:: OnDraw](#ondraw)|( [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)をオーバーライドします)。|
|[CMFCRibbonCheckBox:: OnDrawMenuImage](#ondrawmenuimage)|( [CMFCRibbonBaseElement:: OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)をオーバーライドします。)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(`CMFCRibbonButton::OnDrawOnList` をオーバーライドします。)|
|[CMFCRibbonCheckBox:: Setのデータ](#setaccdata)|( [CMFCRibbonButton:: setのデータ](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)をオーバーライドします)。|

## <a name="remarks"></a>コメント

`CMFCRibbonCheckBox` をアプリケーションで使用するには、次のコンストラクターをコードに追加します。

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

ここで、 *nID*はチェックボックスのコマンド ID で、 *lpszText*はチェックボックスのテキストラベルです。

[CMFCRibbonPanel:: add](../../mfc/reference/cmfcribbonpanel-class.md#add)を使用して、リボンパネルにチェックボックスを追加できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribboncheckbox

##  <a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox

リボンのチェックボックスオブジェクトのコンストラクター

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からコマンド ID を指定します。

*lpszText*<br/>
からテキストラベルを指定します。

### <a name="return-value"></a>戻り値

リボンのチェックボックスオブジェクトを構築します。

### <a name="example"></a>例

次の例は、`CMFCRibbonCheckBox` クラスのオブジェクトを構築する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

##  <a name="getcompactsize"></a>CMFCRibbonCheckBox:: GetCompactSize

オーバーライドされると、チェックボックスのコンパクトなサイズを取得します。

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からチェックボックスに関連付けられている CDC へのポインター。

### <a name="return-value"></a>戻り値

チェックボックスのコンパクトサイズを格納している `CSize` オブジェクトを返します。

### <a name="remarks"></a>コメント

オーバーライドされていない場合は、チェックボックスの中間サイズを返します。

##  <a name="getintermediatesize"></a>CMFCRibbonCheckBox:: GetIntermediateSize

チェックボックスの中間サイズを取得します。

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からこのチェックボックスに関連付けられている CDC へのポインター。

### <a name="return-value"></a>戻り値

チェックボックスの中間サイズを格納している `CSize` オブジェクト。

### <a name="remarks"></a>コメント

オーバーライドされていない場合、は既定のチェックボックスのサイズ (`AFX_CHECK_BOX_DEFAULT_SIZE`) とテキストサイズ、および余白を組み合わせて中間サイズを計算します。

##  <a name="getregularsize"></a>CMFCRibbonCheckBox:: GetRegularSize

チェックボックスの標準のサイズを取得します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からこのチェックボックスに関連付けられている CDC オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

チェックボックスの標準サイズを格納している `CSize` オブジェクトを返します。

### <a name="remarks"></a>コメント

オーバーライドされていない場合は、チェックボックスの中間サイズを返します。

##  <a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage

チェックボックスに関連付けられているツールヒントイメージがあるかどうかを示します。

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>戻り値

チェックボックスに関連付けられているツールヒントイメージがある場合は TRUE を返し、そうでない場合は FALSE を返します。

### <a name="remarks"></a>コメント

##  <a name="ondraw"></a>CMFCRibbonCheckBox:: OnDraw

指定されたデバイスコンテキストを使用してチェックボックスを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からチェックボックスの描画先となる CDC へのポインター。

### <a name="remarks"></a>コメント

##  <a name="ondrawmenuimage"></a>CMFCRibbonCheckBox:: OnDrawMenuImage

チェックボックスのメニューイメージを描画するためにフレームワークによって呼び出されます。

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>パラメーター

から*CDC&#42;*<br/>
チェックボックスに関連付けられている CDC へのポインター。

*CRect*<br/>
からメニューイメージを描画する四角形を指定する `CRect` オブジェクト。

### <a name="return-value"></a>戻り値

イメージが描画された場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>コメント

オーバーライドされていない場合、は FALSE を返します。

##  <a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawOnList

コマンドリストボックスにチェックボックスを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からチェックボックスを描画するデバイスコンテキストへのポインター。

*strText*<br/>
から表示テキスト。

*nTextOffset*<br/>
からリストボックスの左側から表示テキストまでの距離 (ピクセル単位)。

*rect*<br/>
からチェックボックスの表示四角形。

*bIsSelected*<br/>
からチェックボックスがオンの場合は TRUE、それ以外の場合は FALSE。

*bHighlighted 表示*<br/>
からチェックボックスが強調表示されている場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>コメント

##  <a name="setaccdata"></a>CMFCRibbonCheckBox:: Setのデータ

チェックボックスのアクセシビリティデータを設定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
チェックボックスの親ウィンドウ。

*data*<br/>
チェックボックスのアクセシビリティデータ。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>コメント

既定では、このメソッドはチェックボックスのアクセシビリティデータを設定し、常に TRUE を返します。 アクセシビリティ データを設定し、成功または失敗を示す値を返すようにするには、このメソッドをオーバーライドします。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)
