---
description: '詳細情報: CMFCRibbonEdit クラス'
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
ms.openlocfilehash: 83920c9779af10861e32ce964e91af767a3d9e96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193103"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit クラス

リボンバーに配置されるエディットコントロールを実装します。

## <a name="syntax"></a>構文

```cpp
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
|[CMFCRibbonEdit:: CanBeStretched](#canbestretched)|コントロールの高さ `CMFCRibbonEdit` をリボン行の高さに垂直方向に拡大できるかどうかを示します。|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|
|[CMFCRibbonEdit:: CopyFrom](#copyfrom)|指定したオブジェクトの状態 `CMFCRibbonEdit` を現在のオブジェクトにコピーし `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: CreateEdit](#createedit)|オブジェクトの新しいテキストボックスを作成し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::D estroyCtrl](#destroyctrl)|`CMFCRibbonEdit` オブジェクトを破棄します。|
|[CMFCRibbonEdit::D ropDownList](#dropdownlist)|リストボックスを下にドロップします。|
|[CMFCRibbonEdit:: Enabl Inbuttons](#enablespinbuttons)|テキストボックスのスピンボタンの範囲を有効にして設定します。|
|[CMFCRibbonEdit:: GetCompactSize](#getcompactsize)|オブジェクトのコンパクトなサイズを取得し `CFMCRibbonEdit` ます。|
|[CMFCRibbonEdit::GetEditText](#getedittext)|テキストボックス内のテキストを取得します。|
|[CMFCRibbonEdit:: GetIntermediateSize](#getintermediatesize)|オブジェクトの中間サイズを取得し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: GetTextAlign](#gettextalign)|テキストボックス内のテキストの配置を取得します。|
|[CMFCRibbonEdit:: GetWidth](#getwidth)|コントロールの幅 (ピクセル単位) を取得し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|コントロールの表示サイズをコンパクトにできるかどうかを示し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: HasFocus](#hasfocus)|コントロールにフォーカスがあるかどうかを示し `CMFCRIbbonEdit` ます。|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|コントロールの表示サイズが大きくなる可能性があるかどうかを示し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|テキストボックスにスピンボタンがあるかどうかを示します。|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|コントロールが強調表示されているかどうかを示し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|コントロールの表示四角形の大きさが変更されたときにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: OnDraw](#ondraw)|コントロールを描画するためにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|コントロールのラベルとイメージを描画するためにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|コマンドリストボックスにコントロールを描画するために、フレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: OnEnable](#onenable)|コントロールを有効または無効にするためにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: OnHighlight 表示](#onhighlight)|ポインターがコントロールの境界内を出入りするときに、フレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::OnKey](#onkey)|ユーザーが keytip を押し、コントロールにフォーカスがあるときにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|`CMFCRibbonEdit`ユーザーがコントロール上でマウスの左ボタンを押したときにコントロールを更新するために、フレームワークによって呼び出されます。|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|ユーザーがマウスの左ボタンを離したときにフレームワークによって呼び出されます。|
|[CMFCRibbonEdit:: OnRTLChanged](#onrtlchanged)|レイアウトの方向が変更されたときにコントロールを更新するために、フレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: OnShow](#onshow)|コントロールを表示または非表示にするためにフレームワークによって呼び出され `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit:: 再描画](#redraw)|コントロールの表示を更新 `CMFCRibbonEdit` します。|
|[CMFCRibbonEdit:: Setのデータ](#setaccdata)|オブジェクトのアクセシビリティデータを設定し `CMFCRibbonEdit` ます。|
|[CMFCRibbonEdit::SetEditText](#setedittext)|テキストボックス内のテキストを設定します。|
|[CMFCRibbonEdit:: SetTextAlign](#settextalign)|テキストボックスのテキストの配置を設定します。|
|[CMFCRibbonEdit:: SetWidth](#setwidth)|コントロールのテキストボックスの幅を設定し `CMFCRibbonEdit` ます。|

## <a name="remarks"></a>解説

## <a name="example"></a>例

次の例では、オブジェクトを構築し `CMFCRibbonEdit` 、エディットコントロールの横にスピンボタンを表示し、エディットコントロールのテキストを設定する方法を示します。 このコードスニペットは、 [MS Office 2007 Demo サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonEdit

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a> CMFCRibbonEdit:: CanBeStretched

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの高さをリボン行の高さに垂直方向に拡大できるかどうかを示します。

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a> CMFCRibbonEdit::CMFCRibbonEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトを構築します。

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
からコントロールのコマンド ID `CMFCRibbonEdit` 。

*nWidth*<br/>
からコントロールのテキストボックスの幅 (ピクセル単位) `CMFCRibbonEdit` 。

*lpszLabel*<br/>
からコントロールのラベル `CMFCRibbonEdit` 。

*nImage*<br/>
からコントロールに使用する小さいイメージのインデックス `CMFCRibbonEdit` 。 小さい画像のコレクションは、親のリボンカテゴリによって維持されます。

### <a name="remarks"></a>解説

この `CMFCRibbonEdit` コントロールでは、大きなイメージは使用されません。

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonEdit:: CopyFrom

指定した [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) オブジェクトの状態を現在の [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) オブジェクトにコピーします。

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
からソース `CMFCRibbonEdit` オブジェクト。

### <a name="remarks"></a>解説

*Src* パラメーターの型はである必要があり `CMFCRibbonEdit` ます。

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a> CMFCRibbonEdit:: CreateEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトの新しいテキストボックスを作成します。

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
からオブジェクトの親ウィンドウへのポインター `CMFCRibbonEdit` 。

*dwEditStyle*<br/>
からテキストボックスのスタイルを指定します。 「解説」に記載されているウィンドウスタイルと、Windows SDK で説明されている [編集コントロールスタイル](/windows/win32/Controls/edit-control-styles) を組み合わせることができます。

### <a name="return-value"></a>戻り値

メソッドが正常に終了した場合は、新しいテキストボックスへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

カスタムテキストボックスを作成するには、派生クラスでこのメソッドをオーバーライドします。

テキストボックスには、次の [ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles) を適用できます。

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a> CMFCRibbonEdit::D estroyCtrl

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトを破棄します。

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>解説

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a> CMFCRibbonEdit::D ropDownList

リストボックスを下にドロップします。

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>解説

既定では、このメソッドは何も行いません。 リストボックスをドロップダウンするには、このメソッドをオーバーライドします。

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a> CMFCRibbonEdit:: Enabl Inbuttons

テキストボックスのスピンボタンの範囲を有効にして設定します。

```cpp
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*N1 日*<br/>
からスピンボタンの最小値。

*N1 日*<br/>
からスピンボタンの最大値。

### <a name="remarks"></a>解説

スピンボタンを使用すると、上下の矢印が表示され、ユーザーは固定された値のセット内を移動できます。

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a> CMFCRibbonEdit:: GetCompactSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトのコンパクトサイズを取得します。

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からオブジェクトのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

### <a name="return-value"></a>戻り値

オブジェクトのコンパクトサイズ `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a> CMFCRibbonEdit::GetEditText

テキストボックス内のテキストを取得します。

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>戻り値

テキストボックス内のテキスト。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonEdit:: GetIntermediateSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトの中間サイズを取得します。

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からオブジェクトのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

### <a name="return-value"></a>戻り値

オブジェクトの中間サイズ `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a> CMFCRibbonEdit:: GetTextAlign

テキストボックス内のテキストの配置を取得します。

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>戻り値

テキストの配置の列挙値。 使用可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

返される値は、次のいずれかの編集コントロールスタイルです。

- 左揃えの **ES_LEFT**

- 中央揃えの **ES_CENTER**

- 右揃えの **ES_RIGHT**

これらのスタイルの詳細については、「 [コントロールスタイルの編集](/windows/win32/Controls/edit-control-styles)」を参照してください。

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a> CMFCRibbonEdit:: GetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの幅 (ピクセル単位) を取得します。

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>パラメーター

*bInFloatyMode*<br/>
から `CMFCRibbonEdit` コントロールが浮動モードの場合は TRUE、それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

コントロールの幅 (ピクセル単位) `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a> CMFCRibbonEdit::HasCompactMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの表示サイズをコンパクトにできるかどうかを示します。

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

既定では、このメソッドは常に TRUE を返します。 このメソッドをオーバーライドして、表示サイズをコンパクトにできるかどうかを示します。

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a> CMFCRibbonEdit:: HasFocus

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスがあるかどうかを示します。

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>戻り値

コントロールにフォーカスがある場合は TRUE `CMFCRibbonEdit` 。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a> CMFCRibbonEdit::HasLargeMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの表示サイズが大きくなる可能性があるかどうかを示します。

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>戻り値

常に FALSE を返します。

### <a name="remarks"></a>解説

既定では、このメソッドは常に FALSE を返します。 このメソッドをオーバーライドして、表示サイズが大きい可能性があるかどうかを示します。

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a> CMFCRibbonEdit::HasSpinButtons

テキストボックスにスピンボタンがあるかどうかを示します。

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>戻り値

テキストボックスにスピンボタンがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a> CMFCRibbonEdit::IsHighlighted

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが強調表示されているかどうかを示します。

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>戻り値

コントロールが強調表示されている場合は TRUE。それ以外の場合は `CMFCRibbonEdit` FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a> CMFCRibbonEdit::OnAfterChangeRect

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの表示四角形の大きさが変更されたときにフレームワークによって呼び出されます。

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からコントロールのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a> CMFCRibbonEdit:: OnDraw

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを描画するためにフレームワークによって呼び出されます。

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からコントロールのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a> CMFCRibbonEdit::OnDrawLabelAndImage

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールのラベルとイメージを描画するために、フレームワークによって呼び出されます。

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からコントロールのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonEdit::OnDrawOnList

コマンドリストボックスに [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) コントロールを描画するために、フレームワークによって呼び出されます。

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
からコントロールのデバイスコンテキストへのポインター `CMFCRibbonEdit` 。

*strText*<br/>
から表示テキスト [](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit クラス") 。

*nTextOffset*<br/>
からリストボックスの左側から表示テキストまでの距離 (ピクセル単位)。

*rect*<br/>
からコントロールの表示四角形 `CMFCRibbonEdit` 。

*bIsSelected*<br/>
からこのパラメーターは使用されません。

*bHighlighted 表示*<br/>
からこのパラメーターは使用されません。

### <a name="remarks"></a>解説

[コマンド] ボックスの一覧には、ユーザーがクイックアクセスツールバーをカスタマイズできるようにするためのリボンコントロールが表示されます。

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a> CMFCRibbonEdit:: OnEnable

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを有効または無効にするためにフレームワークによって呼び出されます。

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からコントロールを有効にする場合は TRUE。コントロールを無効にする場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a> CMFCRibbonEdit:: OnHighlight 表示

ポインターが [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) コントロールの境界内に出入りするときに、フレームワークによって呼び出されます。

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>パラメーター

*bHighlight 表示*<br/>
からポインターがコントロールの境界内にある場合は TRUE。それ以外の場合は `CMFCRibbonEdit` FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a> CMFCRibbonEdit::OnKey

ユーザーが keytip を押し、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) コントロールにフォーカスがあるときにフレームワークによって呼び出されます。

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>パラメーター

*bIsMenuKey*<br/>
からKeytip にポップアップメニューが表示される場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

イベントが処理された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a> CMFCRibbonEdit::OnLButtonDown

ユーザーがコントロール上でマウスの左ボタンを押したときに [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) コントロールを更新するために、フレームワークによって呼び出されます。

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
からこのパラメーターは使用されません。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a> CMFCRibbonEdit::OnLButtonUp

ユーザーがマウスの左ボタンを離したときにフレームワークによって呼び出されます。

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
からこのパラメーターは使用されません。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a> CMFCRibbonEdit:: OnRTLChanged

レイアウトの方向が変更されたときに [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) コントロールを更新するために、フレームワークによって呼び出されます。

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>パラメーター

*bIsRTL*<br/>
からレイアウトが右から左の場合は TRUE。レイアウトが左から右への場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a> CMFCRibbonEdit:: OnShow

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールを表示または非表示にするためにフレームワークによって呼び出されます。

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
からコントロールを表示する場合は TRUE。コントロールを非表示にする場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a> CMFCRibbonEdit:: 再描画

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールの表示を更新します。

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>解説

このメソッド `CMFCRibbonEdit` は、RDW_INVALIDATE、RDW_ERASE、および RDW_UPDATENOW フラグが設定された状態で [CWnd:: RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) を間接的に呼び出すことによって、オブジェクトの表示四角形を再描画します。

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonEdit:: Setのデータ

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクトのアクセシビリティデータを設定します。

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
オブジェクトの親ウィンドウへのポインター `CMFCRibbonEdit` 。

*data*<br/>
オブジェクトのアクセシビリティデータ `CMFCRibbonEdit` 。

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a> CMFCRibbonEdit::SetEditText

テキストボックス内のテキストを設定します。

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>パラメーター

*strText*<br/>
からテキストボックスのテキスト。

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a> CMFCRibbonEdit:: SetTextAlign

テキストボックスのテキストの配置を設定します。

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>パラメーター

*n Align*<br/>
からテキストの配置の列挙値。 使用可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

パラメーター *n align* は、次のいずれかの編集コントロールスタイルです。

- 左揃えの ES_LEFT

- 中央揃えの ES_CENTER

- 右揃えの ES_RIGHT

これらのスタイルの詳細については、「 [コントロールスタイルの編集](/windows/win32/Controls/edit-control-styles)」を参照してください。

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a> CMFCRibbonEdit:: SetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールのテキストボックスの幅を設定します。

```cpp
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
からテキストボックスの幅 (ピクセル単位)。

*bInFloatyMode*<br/>
フローティングモードの幅を設定する場合は TRUE。標準モードの幅を設定する場合は FALSE。

### <a name="remarks"></a>解説

`CMFCRibbonEdit`コントロールには、表示モード (フローティングモードと通常モード) に応じて2つの幅があります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
