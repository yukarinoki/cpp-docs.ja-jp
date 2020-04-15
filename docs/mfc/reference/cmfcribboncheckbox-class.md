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
ms.openlocfilehash: 089c8056afebef31ff98a435bf145566ae64fe1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375250"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox クラス

`CMFCRibbonCheckBox` クラスは、リボン パネル、クイック アクセス ツール バー、またはポップアップ メニューに追加できるチェック ボックスを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(オーバーライド[CMFCリボンボタン::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(オーバーライド[CMFC リボンボタン::取得中間サイズ](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(オーバーライド[CMFCリボンボタン::取得レギュラーサイズ](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`をオーバーライドします)。|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(オーバーライド[CMFCリボンボタン::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(オーバーライドします[。](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|( `CMFCRibbonButton::OnDrawOnList`をオーバーライドします)。|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(オーバーライド[CMFCリボンボタン:::セットアックデータ](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>解説

`CMFCRibbonCheckBox` をアプリケーションで使用するには、次のコンストラクターをコードに追加します。

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

*ここで nID*はチェック ボックス コマンド ID、lpszText はチェック ボックスのテキスト ラベルです。 *lpszText*

チェック ボックスをリボン パネルに追加するには[、CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)を使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribboncheckbox.h

## <a name="cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a>CMFCリボンチェックボックス::CMFCリボンチェックボックス

リボン チェック ボックス オブジェクトのコンストラクター

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]コマンド ID を指定します。

*lpszText*<br/>
[in]テキスト ラベルを指定します。

### <a name="return-value"></a>戻り値

リボン チェック ボックス オブジェクトを作成します。

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCRibbonCheckBox`示します。

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

## <a name="cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a>チェック ボックス::ゲットコンパクトサイズ

オーバーライドされた場合、チェック ボックスのコンパクト サイズを取得します。

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]チェック ボックスに関連付けられている CDC へのポインター。

### <a name="return-value"></a>戻り値

チェック`CSize`ボックスのコンパクト サイズを含むオブジェクトを返します。

### <a name="remarks"></a>解説

オーバーライドされていない場合は、チェック ボックスの中間サイズを返します。

## <a name="cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a>チェック ボックス::取得中間サイズ

チェック ボックスの中間サイズを取得します。

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]このチェック ボックスに関連付けられている CDC へのポインター。

### <a name="return-value"></a>戻り値

チェック`CSize`ボックスの中間サイズを格納しているオブジェクト。

### <a name="remarks"></a>解説

オーバーライドされない場合は、中間サイズを既定のチェック ボックス サイズ ( `AFX_CHECK_BOX_DEFAULT_SIZE`) にテキスト サイズと余白を加えた値として計算します。

## <a name="cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a>チェック ボックス::ゲットレギュラーサイズ

チェック ボックスの標準サイズを取得します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]このチェック ボックスに関連付けられている CDC オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

チェック`CSize`ボックスの標準サイズを含むオブジェクトを返します。

### <a name="remarks"></a>解説

オーバーライドされていない場合は、チェック ボックスの中間サイズを返します。

## <a name="cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>チェック ボックス::イドロー ツールヒントイメージ

チェック ボックスに関連付けられているツールヒント イメージがあるかどうかを示します。

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>戻り値

チェック ボックスに関連付けられているツールヒントイメージがある場合は TRUE を返し、関連付けられていない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboncheckboxondraw"></a><a name="ondraw"></a>CMFCリボンチェックボックス::オンドロー

指定したデバイス コンテキストを使用してチェック ボックスを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]チェック ボックスを描画する CDC へのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a>チェック ボックス::オンドローメニューイメージ

チェック ボックスのメニュー イメージを描画するために、フレームワークによって呼び出されます。

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>パラメーター

[in]*CDC&#42;*<br/>
チェック ボックスに関連付けられている CDC へのポインター。

*CRect*<br/>
[in]メニュー`CRect`イメージを描画する四角形を指定するオブジェクト。

### <a name="return-value"></a>戻り値

イメージが描画された場合は TRUE を返し、描画されなかった場合は FALSE を返します。

### <a name="remarks"></a>解説

オーバーライドされない場合は FALSE を返します。

## <a name="cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a>チェック ボックス::オンドローオンリスト

コマンド リスト ボックスにチェック ボックスを描画するために、フレームワークによって呼び出されます。

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
[in]チェック ボックスを描画するデバイス コンテキストへのポインター。

*str テキスト*<br/>
[in]表示テキスト。

*オフセット*<br/>
[in]リスト ボックスの左側から表示テキストまでの距離 (ピクセル単位)。

*Rect*<br/>
[in]チェック ボックスの表示四角形。

*bIsSelected*<br/>
[in]チェック ボックスがオンの場合は TRUE、オンでない場合は FALSE。

*b強調表示*<br/>
[in]チェック ボックスが強調表示されている場合は TRUE、強調表示されていない場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a>チェック ボックス::セットアックデータ

チェック ボックスのアクセシビリティ データを設定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
チェック ボックスの親ウィンドウ。

*データ*<br/>
チェック ボックスのアクセシビリティ データ。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

既定では、このメソッドはチェック ボックスのアクセシビリティ データを設定し、常に TRUE を返します。 アクセシビリティ データを設定し、成功または失敗を示す値を返すようにするには、このメソッドをオーバーライドします。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonpanel-class.md)
