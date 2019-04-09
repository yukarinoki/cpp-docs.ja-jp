---
title: CMFCRibbonEdit クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: 80ee43ae32416f9f62df419c4afbd46a0aa63cc8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780484"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit クラス

リボン バー上にある編集コントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|示すかどうかの高さ、`CMFCRibbonEdit`リボンの行の高さにコントロールを縦に拡大できます。|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|指定した状態をコピー`CMFCRibbonEdit`現在オブジェクト`CMFCRibbonEdit`オブジェクト。|
|[CMFCRibbonEdit::CreateEdit](#createedit)|新しいテキスト ボックスを作成、`CMFCRibbonEdit`オブジェクト。|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|`CMFCRibbonEdit` オブジェクトを破棄します。|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|リスト ボックスの一覧を削除します。|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|コンパクト サイズを取得、`CFMCRibbonEdit`オブジェクト。|
|[CMFCRibbonEdit::GetEditText](#getedittext)|テキスト ボックス内のテキストを取得します。|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|中間のサイズを取得、`CMFCRibbonEdit`オブジェクト。|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|テキスト ボックス内のテキストの配置を取得します。|
|[CMFCRibbonEdit::GetWidth](#getwidth)|幅 (ピクセル単位) を取得、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|示すための表示のサイズかどうか、`CMFCRibbonEdit`コントロールは、コンパクトであることができます。|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|示すかどうか、`CMFCRIbbonEdit`コントロールにフォーカスします。|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|示すための表示のサイズかどうか、`CMFCRibbonEdit`コントロールが大きくなることができます。|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|スピン ボタンがテキスト ボックスにあるかどうかを示します。|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|示すかどうか、`CMFCRibbonEdit`コントロールが強調表示されます。|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|フレームワークによって呼び出されるときに表示する四角形の大きさ、`CMFCRibbonEdit`コントロールが変更。|
|[CMFCRibbonEdit::OnDraw](#ondraw)|描画するためにフレームワークによって呼び出されます、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|イメージのラベルを描画およびフレームワークによって呼び出されます、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|描画するためにフレームワークによって呼び出されます、`CMFCRibbonEdit`コマンド リスト ボックス内のコントロール。|
|[CMFCRibbonEdit::OnEnable](#onenable)|有効または無効にするためにフレームワークによって呼び出される、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|ポインターの出入りの境界から出るときに、フレームワークによって呼び出されます、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::OnKey](#onkey)|Keytip を押したときに、フレームワークによって呼び出されます、`CMFCRibbonEdit`コントロールにフォーカスします。|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|更新するためにフレームワークによって呼び出されます、`CMFCRibbonEdit`ユーザーがコントロールでマウスの左ボタンを押したときを制御します。|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|更新するためにフレームワークによって呼び出される、`CMFCRibbonEdit`レイアウトの方向変更されたときを制御します。|
|[CMFCRibbonEdit::OnShow](#onshow)|表示または非表示にするために、フレームワークによって呼び出される、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::Redraw](#redraw)|表示を更新、`CMFCRibbonEdit`コントロール。|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|アクセシビリティ データを設定、`CMFCRibbonEdit`オブジェクト。|
|[CMFCRibbonEdit::SetEditText](#setedittext)|テキスト ボックスにテキストを設定します。|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|テキスト ボックスのテキストの配置を設定します。|
|[CMFCRibbonEdit::SetWidth](#setwidth)|テキスト ボックスの幅を設定、`CMFCRibbonEdit`コントロール。|

## <a name="remarks"></a>Remarks

## <a name="example"></a>例

次の例は、構築する方法を示します、`CMFCRibbonEdit`オブジェクトで、編集コントロールの横にあるスピン ボタンを表示し、編集コントロールのテキストを設定します。 このコード スニペットの一部、 [MS Office 2007 のデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonEdit.h

##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched

示すかどうかの高さ、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールは、リボンの行の高さを縦に拡大できます。

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>Remarks

##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit

構築、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]コマンドの ID、`CMFCRibbonEdit`コントロール。

*nWidth*<br/>
[in]幅 (ピクセル単位) のテキスト ボックス、`CMFCRibbonEdit`コントロール。

*lpszLabel*<br/>
[in]ラベル、`CMFCRibbonEdit`コントロール。

*nImage*<br/>
[in]使用する小さいイメージのインデックス、`CMFCRibbonEdit`コントロール。 小さいイメージのコレクションは、親のリボン カテゴリによって管理されます。

### <a name="remarks"></a>Remarks

`CMFCRibbonEdit`コントロールで大きいイメージを使用しません。

##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom

指定した状態をコピー [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)現在オブジェクト[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]ソース`CMFCRibbonEdit`オブジェクト。

### <a name="remarks"></a>Remarks

*Src*パラメーター型でなければなりません`CMFCRibbonEdit`します。

##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit

新しいテキスト ボックスを作成、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクト。

*dwEditStyle*<br/>
[in]テキスト ボックスのスタイルを指定します。 「解説」セクションに記載のウィンドウ スタイルを組み合わせることができます、[コントロール スタイルを編集](/windows/desktop/Controls/edit-control-styles)Windows sdk に記載されています。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、新しいテキスト ボックスへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

カスタムのテキスト ボックスを作成する派生クラスでこのメソッドをオーバーライドします。

次を適用する[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)をテキスト ボックス。

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl

破棄、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Remarks

##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList

リスト ボックスの一覧を削除します。

```
virtual void DropDownList();
```

### <a name="remarks"></a>Remarks

既定では、このメソッドは何もしません。 ドロップダウン リスト ボックスには、このメソッドをオーバーライドします。

##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons

有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
[in]スピン ボタンの最小値。

*nMax*<br/>
[in]スピン ボタンの最大値。

### <a name="remarks"></a>Remarks

スピン ボタンは表示下矢印をクリックし、値の固定セットを移動するユーザーを有効にします。

##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize

コンパクト サイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクト。

### <a name="return-value"></a>戻り値

コンパクト サイズ、`CMFCRibbonEdit`オブジェクト。

### <a name="remarks"></a>Remarks

##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText

テキスト ボックス内のテキストを取得します。

```
CString GetEditText() const;
```

### <a name="return-value"></a>戻り値

テキスト ボックス内のテキスト。

### <a name="remarks"></a>Remarks

##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize

中間のサイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクト。

### <a name="return-value"></a>戻り値

中間のサイズ、`CMFCRibbonEdit`オブジェクト。

### <a name="remarks"></a>Remarks

##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign

テキスト ボックス内のテキストの配置を取得します。

```
int GetTextAlign() const;
```

### <a name="return-value"></a>戻り値

テキストの配置の列挙値。 使用可能な値は、「解説」を参照してください。

### <a name="remarks"></a>Remarks

返される値は、次の編集コントロールのスタイルのいずれかです。

- **ES_LEFT**左揃え

- **ES_CENTER**の中央揃え

- **ES_RIGHT**右揃え

これらのスタイルの詳細については、次を参照してください。[編集コントロールのスタイル](/windows/desktop/Controls/edit-control-styles)します。

##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth

幅 (ピクセル単位) を取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>パラメーター

*bInFloatyMode*<br/>
[in]TRUE の場合、`CMFCRibbonEdit`コントロールが浮動小数点モードです。 それ以外の場合、FALSE。

### <a name="return-value"></a>戻り値

幅 (ピクセル単位) の`CMFCRibbonEdit`コントロール。

### <a name="remarks"></a>Remarks

##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode

示すための表示のサイズかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールは、コンパクトであることができます。

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>Remarks

既定では、このメソッドは常に TRUE を返します。 表示サイズを縮小できるかどうかを示すには、このメソッドをオーバーライドします。

##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus

示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスします。

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、`CMFCRibbonEdit`コントロールにフォーカスがある場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode

示すための表示のサイズかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが大きくなることができます。

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>Remarks

既定でこのメソッドは常に FALSE を返します。 表示サイズが大きいかどうかを示すには、このメソッドをオーバーライドします。

##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons

スピン ボタンがテキスト ボックスにあるかどうかを示します。

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、テキスト ボックスに、スピン ボタンそれ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted

示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが強調表示されます。

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、`CMFCRibbonEdit`コントロールが強調表示されている場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect

フレームワークによって呼び出されますとを表示する四角形の大きさ、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)変更を制御します。

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。

### <a name="remarks"></a>Remarks

##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw

描画するためにフレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。

### <a name="remarks"></a>Remarks

##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage

イメージのラベルを描画およびフレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。

### <a name="remarks"></a>Remarks

##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList

描画するためにフレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コマンド リスト ボックス内のコントロール。

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
[in]デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。

*strText*<br/>
[in]表示テキスト[ ] (../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit クラス")します。

*nTextOffset*<br/>
[in]距離 (ピクセル)、テキストを表示、リスト ボックスの左側にあるからです。

*rect*<br/>
[in]表示する四角形、`CMFCRibbonEdit`コントロール。

*bIsSelected*<br/>
[in]このパラメーターは使用されません。

*bHighlighted*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>Remarks

コマンドのリスト ボックスには、クイック アクセス ツールバーをカスタマイズするユーザーを有効にするリボン コントロールが表示されます。

##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable

有効または無効にするためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]コントロールを有効にする場合は TRUEコントロールを無効にする場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight

ポインターの出入りの境界から出るときに、フレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bHighlight*<br/>
[in]ポインターがの境界内にある場合は TRUE、`CMFCRibbonEdit`制御します。 それ以外の場合、FALSE。

### <a name="remarks"></a>Remarks

##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey

Keytip を押したときに、フレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスします。

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>パラメーター

*bIsMenuKey*<br/>
[in]Keytip がポップアップ メニューが表示される場合は TRUE。それ以外の場合、FALSE です。

### <a name="return-value"></a>戻り値

イベントが処理された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown

更新するためにフレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)ユーザーがコントロールでマウスの左ボタンを押したときを制御します。

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>Remarks

##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp

ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>Remarks

##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged

更新するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)レイアウトの方向変更されたときを制御します。

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>パラメーター

*bIsRTL*<br/>
[in]レイアウトは右から左の場合は TRUE。レイアウトが左から右の場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow

表示または非表示にするために、フレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
[in]コントロールを表示する場合は TRUEコントロールを非表示にする場合は FALSE。

### <a name="remarks"></a>Remarks

##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw

表示を更新、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
virtual void Redraw();
```

### <a name="remarks"></a>Remarks

このメソッドを表示する四角形を再描画、`CMFCRibbonEdit`オブジェクトを直接呼び出す[CWnd::RedrawWindow](/windows/desktop/api/winuser/nf-winuser-redrawwindow) RDW_INVALIDATE、RDW_ERASE、および RDW_UPDATENOW フラグを設定します。

##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData

アクセシビリティ データを設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクト。

*data*<br/>
アクセシビリティ データを`CMFCRibbonEdit`オブジェクト。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>Remarks

##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText

テキスト ボックスにテキストを設定します。

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>パラメーター

*strText*<br/>
[in]テキスト ボックスのテキスト。

##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign

テキスト ボックスのテキストの配置を設定します。

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>パラメーター

*nAlign*<br/>
[in]テキストの配置の列挙値。 使用可能な値は、「解説」を参照してください。

### <a name="remarks"></a>Remarks

パラメーター *nAlign*コントロールのスタイルは、次の編集のいずれか。

- 左揃えの ES_LEFT

- 中央揃えの ES_CENTER

- 右揃えの ES_RIGHT

これらのスタイルの詳細については、次を参照してください。[編集コントロールのスタイル](/windows/desktop/Controls/edit-control-styles)します。

##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth

テキスト ボックスの幅を設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
[in]テキスト ボックスのピクセル単位の幅。

*bInFloatyMode*<br/>
浮動小数点モードの幅を設定する場合は TRUE通常モードの幅を設定する場合は FALSE。

### <a name="remarks"></a>Remarks

`CMFCRibbonEdit`コントロールが 2 つの幅の表示モードに応じて: 浮動モードと通常モードです。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
