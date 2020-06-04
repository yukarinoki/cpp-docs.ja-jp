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
ms.openlocfilehash: ab621a05f9b658eee9babb14e257680fa95e0f96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375176"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit クラス

リボン バーにあるエディット コントロールを実装します。

## <a name="syntax"></a>構文

```cpp
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を編集します。](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCリボン編集::缶詰ストレッチ](#canbestretched)|コントロールの高さがリボン行`CMFCRibbonEdit`の高さに合うかどうかを示します。|
|[を編集します。](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|
|[コMFCリボン編集::コピー元](#copyfrom)|指定した`CMFCRibbonEdit`オブジェクトの状態を現在`CMFCRibbonEdit`のオブジェクトにコピーします。|
|[編集::編集](#createedit)|オブジェクトの新しいテキスト ボックス`CMFCRibbonEdit`を作成します。|
|[:DエストロイCtrl](#destroyctrl)|`CMFCRibbonEdit` オブジェクトを破棄します。|
|[:Dリスト](#dropdownlist)|リスト ボックスをドロップダウンします。|
|[をクリックします。](#enablespinbuttons)|テキスト ボックスのスピン ボタンの範囲を有効にして設定します。|
|[をクリックします。](#getcompactsize)|オブジェクトのコンパクト サイズを`CFMCRibbonEdit`取得します。|
|[テキストを編集します。](#getedittext)|テキスト ボックス内のテキストを取得します。|
|[を編集します。](#getintermediatesize)|オブジェクトの中間サイズを`CMFCRibbonEdit`取得します。|
|[編集::テキスト整列](#gettextalign)|テキスト ボックス内のテキストの配置を取得します。|
|[を編集します。](#getwidth)|コントロールの幅 (ピクセル単位) を`CMFCRibbonEdit`取得します。|
|[をクリックします。](#hascompactmode)|コントロールの表示サイズを`CMFCRibbonEdit`コンパクトにできるかどうかを示します。|
|[をクリックします。](#hasfocus)|コントロールに`CMFCRIbbonEdit`フォーカスがあるかどうかを示します。|
|[を編集します。](#haslargemode)|コントロールの表示サイズが`CMFCRibbonEdit`大きくなるかどうかを示します。|
|[CMFCリボン編集::ハススピンボタン](#hasspinbuttons)|テキスト ボックスにスピン ボタンがあるかどうかを示します。|
|[CMFCリボン編集::ハイライト](#ishighlighted)|コントロールが`CMFCRibbonEdit`強調表示されているかどうかを示します。|
|[コントロールの後に編集します。](#onafterchangerect)|コントロールの表示四角形のサイズが変更されたときに、フレームワークによって`CMFCRibbonEdit`呼び出されます。|
|[をクリックします。](#ondraw)|コントロールを描画するために、フレームワークによって`CMFCRibbonEdit`呼び出されます。|
|[をクリックします。](#ondrawlabelandimage)|コントロールのラベルとイメージを描画するために、フレームワークによって呼`CMFCRibbonEdit`び出されます。|
|[をクリックします。](#ondrawonlist)|コマンド リスト ボックスにコントロール`CMFCRibbonEdit`を描画するために、フレームワークによって呼び出されます。|
|[を有効にする](#onenable)|コントロールを有効または無効にするために、フレームワークによって`CMFCRibbonEdit`呼び出されます。|
|[CMFCリボン編集::オンハイライト](#onhighlight)|ポインターがコントロールの境界に入るか、またはコントロールの境界から離れたとき`CMFCRibbonEdit`に、フレームワークによって呼び出されます。|
|[キーの編集::オンキー](#onkey)|ユーザーがキーヒントを押し、コントロールにフォーカスがあるときに`CMFCRibbonEdit`、フレームワークによって呼び出されます。|
|[コントロールメニュー::オンルボタンダウン](#onlbuttondown)|ユーザーがコントロールの左マウス`CMFCRibbonEdit`ボタンを押したときにコントロールを更新するために、フレームワークによって呼び出されます。|
|[コントロールの上](#onlbuttonup)|ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。|
|[コントロールの編集::オントレル変更](#onrtlchanged)|レイアウトの方向が変更されたときにコントロール`CMFCRibbonEdit`を更新するために、フレームワークによって呼び出されます。|
|[CMFCリボン編集::オンショー](#onshow)|コントロールを表示または非表示にするために、フレームワークによって`CMFCRibbonEdit`呼び出されます。|
|[再描画](#redraw)|コントロールの表示を`CMFCRibbonEdit`更新します。|
|[をクリックします。](#setaccdata)|オブジェクトのアクセシビリティ データを`CMFCRibbonEdit`設定します。|
|[テキストを編集します。](#setedittext)|テキスト ボックス内のテキストを設定します。|
|[編集::テキスト整列の設定](#settextalign)|テキスト ボックスのテキストの配置を設定します。|
|[コントロールの幅を変更します。](#setwidth)|コントロールのテキスト ボックスの幅を`CMFCRibbonEdit`設定します。|

## <a name="remarks"></a>解説

## <a name="example"></a>例

`CMFCRibbonEdit`オブジェクトの作成方法、編集コントロールの横にスピン ボタンを表示する方法、およびエディット コントロールのテキストを設定する方法を次の例に示します。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxRibbonEdit.h

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFCリボン編集::缶詰ストレッチ

[コントロールの](../../mfc/reference/cmfcribbonedit-class.md)高さをリボン行の高さに垂直方向に上げることができるかどうかを示します。

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>を編集します。

オブジェクトを構築[します](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]コントロールの`CMFCRibbonEdit`コマンド ID。

*n幅*<br/>
[in]`CMFCRibbonEdit`コントロールのテキスト ボックスの幅 (ピクセル単位)。

*ラベル*<br/>
[in]コントロールの`CMFCRibbonEdit`ラベル。

*nイメージ*<br/>
[in]コントロールに使用する小さいイメージの`CMFCRibbonEdit`インデックス。 小さいイメージのコレクションは、親リボン カテゴリによって管理されます。

### <a name="remarks"></a>解説

コントロール`CMFCRibbonEdit`は大きなイメージを使用しません。

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>コMFCリボン編集::コピー元

指定した[CMFC リボンエディット](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトの状態を現在の[CMFC リボンエディット](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトにコピーします。

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]ソース`CMFCRibbonEdit`オブジェクト。

### <a name="remarks"></a>解説

*src*パラメータは型`CMFCRibbonEdit`でなければなりません。

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a>編集::編集

オブジェクトの新しいテキスト ボックス[を作成します](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]`CMFCRibbonEdit`オブジェクトの親ウィンドウへのポインター。

*ドウエディットスタイル*<br/>
[in]テキスト ボックスのスタイルを指定します。 「解説」に記載されているウィンドウ スタイルと、Windows SDK で説明されている[エディット コントロール スタイル](/windows/win32/Controls/edit-control-styles)を組み合わせることができます。

### <a name="return-value"></a>戻り値

メソッドが正常に終了した場合は、新しいテキスト ボックスへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

カスタム テキスト ボックスを作成するには、派生クラスでこのメソッドをオーバーライドします。

次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)をテキスト ボックスに適用できます。

- **Ws_child**

- **Ws_visible**

- **WS_DISABLED**

- **Ws_group**

- **WS_TABSTOP**

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>:DエストロイCtrl

[オブジェクトを](../../mfc/reference/cmfcribbonedit-class.md)破棄します。

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>解説

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>:Dリスト

リスト ボックスをドロップダウンします。

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>解説

既定では、このメソッドは何も実行しません。 リスト ボックスをドロップダウンするには、このメソッドをオーバーライドします。

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>をクリックします。

テキスト ボックスのスピン ボタンの範囲を有効にして設定します。

```cpp
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
[in]スピン ボタンの最小値。

*nMax*<br/>
[in]スピン ボタンの最大値。

### <a name="remarks"></a>解説

スピン ボタンは上下の矢印を表示し、ユーザーが固定された値のセットを移動できるようにします。

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>をクリックします。

オブジェクトのコンパクト サイズを取得[します](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonEdit`オブジェクトのデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

`CMFCRibbonEdit`オブジェクトのコンパクト サイズ。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a>テキストを編集します。

テキスト ボックス内のテキストを取得します。

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>戻り値

テキスト ボックス内のテキスト。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>を編集します。

オブジェクトの中間サイズ[を](../../mfc/reference/cmfcribbonedit-class.md)取得します。

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonEdit`オブジェクトのデバイス コンテキストへのポインター。

### <a name="return-value"></a>戻り値

`CMFCRibbonEdit`オブジェクトの中間サイズ。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a>編集::テキスト整列

テキスト ボックス内のテキストの配置を取得します。

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>戻り値

テキストの配置列挙値。 可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

戻り値は、次のエディット コントロール スタイルのいずれかです。

- 左揃えの**ES_LEFT**

- 中心の配置の**ES_CENTER**

- 右揃えのための**ES_RIGHT**

これらのスタイルの詳細については、「コントロール[スタイルの編集](/windows/win32/Controls/edit-control-styles)」を参照してください。

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a>を編集します。

[コントロールの](../../mfc/reference/cmfcribbonedit-class.md)幅をピクセル単位で取得します。

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>パラメーター

*ブインフローティモード*<br/>
[in]コントロールが`CMFCRibbonEdit`フローティング モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

`CMFCRibbonEdit`コントロールの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>をクリックします。

[コントロールの](../../mfc/reference/cmfcribbonedit-class.md)表示サイズをコンパクトにできるかどうかを示します。

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

既定では、このメソッドは常に TRUE を返します。 表示サイズをコンパクトにできるかどうかを示すには、このメソッドをオーバーライドします。

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a>をクリックします。

[コントロールに](../../mfc/reference/cmfcribbonedit-class.md)フォーカスがあるかどうかを示します。

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

コントロールに`CMFCRibbonEdit`フォーカスがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>を編集します。

[コントロールの](../../mfc/reference/cmfcribbonedit-class.md)表示サイズが大きくなるかどうかを示します。

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>解説

既定では、このメソッドは常に FALSE を返します。 表示サイズが大きくなるかどうかを示すには、このメソッドをオーバーライドします。

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFCリボン編集::ハススピンボタン

テキスト ボックスにスピン ボタンがあるかどうかを示します。

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>戻り値

テキスト ボックスにスピン ボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFCリボン編集::ハイライト

[コントロールが](../../mfc/reference/cmfcribbonedit-class.md)強調表示されているかどうかを示します。

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

コントロールが`CMFCRibbonEdit`強調表示されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>コントロールの後に編集します。

[コントロールの変更を表示](../../mfc/reference/cmfcribbonedit-class.md)する四角形のサイズをフレームワークによって呼び出します。

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonEdit`コントロールのデバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a>をクリックします。

コントロールを描画するためにフレームワークによって呼び出[されます](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonEdit`コントロールのデバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>をクリックします。

コントロールのラベルとイメージを描画するために、フレームワークによって呼び出[されます](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]`CMFCRibbonEdit`コントロールのデバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>をクリックします。

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールをコマンド リスト ボックスに描画するために、フレームワークによって呼び出されます。

```cpp
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
[in]`CMFCRibbonEdit`コントロールのデバイス コンテキストへのポインター。

*str テキスト*<br/>
[in]表示テキスト[](../../mfc/reference/cmfcribbonedit-class.md "クラス")。

*オフセット*<br/>
[in]リスト ボックスの左側から表示テキストまでの距離 (ピクセル単位)。

*Rect*<br/>
[in]`CMFCRibbonEdit`コントロールの表示四角形。

*bIsSelected*<br/>
[in]このパラメーターは使用されません。

*b強調表示*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>解説

コマンド リスト ボックスには、クイック アクセス ツールバーをカスタマイズするためのリボン コントロールが表示されます。

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a>を有効にする

を有効または無効にするフレームワークによって呼び出されます[、 CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]コントロールを有効にする場合は TRUE。FALSE を指定すると、コントロールが無効になります。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFCリボン編集::オンハイライト

ポインターが[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの境界に入るか、または離れたときに、フレームワークによって呼び出されます。

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bハイライト*<br/>
[in]ポインターが`CMFCRibbonEdit`コントロールの境界内にある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a>キーの編集::オンキー

ユーザーがキーヒントを押し[、CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスがあるときに、フレームワークによって呼び出されます。

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>パラメーター

*メニューキー*<br/>
[in]キーヒントにポップアップ メニューが表示される場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

イベントが処理された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>コントロールメニュー::オンルボタンダウン

ユーザーがコントロールのマウスの左ボタンを押したときに[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを更新するために、フレームワークによって呼び出されます。

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>コントロールの上

ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]このパラメーターは使用されません。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>コントロールの編集::オントレル変更

レイアウトの方向が変更されたときに[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを更新するために、フレームワークによって呼び出されます。

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>パラメーター

*ビストルトル*<br/>
[in]レイアウトが右から左に表示される場合は TRUE。レイアウトが左から右の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a>CMFCリボン編集::オンショー

コントロールを表示または非表示にするフレームワークによって呼び出[されます](../../mfc/reference/cmfcribbonedit-class.md)。

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]コントロールを表示する場合は TRUE。FALSE を指定すると、コントロールが非表示になります。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a>再描画

[コントロールの](../../mfc/reference/cmfcribbonedit-class.md)表示を更新します。

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>解説

このメソッドは、RDW_INVALIDATE、RDW_ERASE、および`CMFCRibbonEdit`RDW_UPDATENOWフラグを設定して[CWnd::RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow)を間接的に呼び出すことによって、オブジェクトの表示四角形を再描画します。

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>をクリックします。

オブジェクトのアクセシビリティ データ[を](../../mfc/reference/cmfcribbonedit-class.md)設定します。

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
`CMFCRibbonEdit`オブジェクトの親ウィンドウへのポインター。

*データ*<br/>
`CMFCRibbonEdit`オブジェクトのアクセシビリティ データ。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a>テキストを編集します。

テキスト ボックス内のテキストを設定します。

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>パラメーター

*str テキスト*<br/>
[in]テキスト ボックスのテキスト。

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a>編集::テキスト整列の設定

テキスト ボックスのテキストの配置を設定します。

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>パラメーター

*nAlign*<br/>
[in]テキストの配置列挙値。 可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

パラメータ*nAlign*は、次のいずれかのエディット コントロール スタイルです。

- 左揃えのES_LEFT

- 中心の配置のES_CENTER

- 右揃えのためのES_RIGHT

これらのスタイルの詳細については、「コントロール[スタイルの編集](/windows/win32/Controls/edit-control-styles)」を参照してください。

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a>コントロールの幅を変更します。

コントロールのテキスト ボックスの幅[を](../../mfc/reference/cmfcribbonedit-class.md)設定します。

```cpp
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
[in]テキスト ボックスの幅 (ピクセル単位)。

*ブインフローティモード*<br/>
フローティング モードの幅を設定する場合は TRUE。通常モードの幅を設定するには FALSE。

### <a name="remarks"></a>解説

コントロール`CMFCRibbonEdit`の表示モードに応じて、フローティング モードと通常モードの 2 つの幅があります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)
