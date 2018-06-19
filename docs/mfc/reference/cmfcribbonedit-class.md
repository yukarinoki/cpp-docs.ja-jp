---
title: CMFCRibbonEdit クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: daa6a5976f4f20ba067eed047a4ff83b30550ea9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374177"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit クラス
リボン バーに配置されるエディット コントロールを実装します。  
  
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
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|示すかどうかの高さ、`CMFCRibbonEdit`コントロールは、リボンの行の高さを縦に拡大できます。|  
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|`CMFCRibbonEdit` オブジェクトを構築します。|  
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|指定した状態をコピー`CMFCRibbonEdit`現在オブジェクト`CMFCRibbonEdit`オブジェクト。|  
|[CMFCRibbonEdit::CreateEdit](#createedit)|新しいテキスト ボックスを作成、`CMFCRibbonEdit`オブジェクト。|  
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|`CMFCRibbonEdit` オブジェクトを破棄します。|  
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|ボックスの一覧を削除します。|  
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。|  
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|コンパクト サイズを取得、`CFMCRibbonEdit`オブジェクト。|  
|[CMFCRibbonEdit::GetEditText](#getedittext)|テキスト ボックス内のテキストを取得します。|  
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|中間サイズを取得、`CMFCRibbonEdit`オブジェクト。|  
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|テキスト ボックス内のテキストの配置を取得します。|  
|[CMFCRibbonEdit::GetWidth](#getwidth)|幅 (ピクセル単位) を取得、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|示すための表示のサイズかどうか、`CMFCRibbonEdit`コントロールは、コンパクトであることができます。|  
|[CMFCRibbonEdit::HasFocus](#hasfocus)|示すかどうか、`CMFCRIbbonEdit`コントロールにフォーカスします。|  
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|示しますのサイズを表示するかどうか、`CMFCRibbonEdit`コントロールが大きくなることができます。|  
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|テキスト ボックスに、スピン ボタンがあるかどうかを示します。|  
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|示すかどうか、`CMFCRibbonEdit`コントロールが強調表示されます。|  
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|フレームワークによって呼び出されますときを表示する四角形の寸法、`CMFCRibbonEdit`変更を制御します。|  
|[CMFCRibbonEdit::OnDraw](#ondraw)|描画するためにフレームワークによって呼び出される、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|ラベルを描画しのイメージに、フレームワークによって呼び出されます、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|描画するためにフレームワークによって呼び出される、`CMFCRibbonEdit`コマンドのリスト ボックス内のコントロールです。|  
|[CMFCRibbonEdit::OnEnable](#onenable)|有効または無効にするためにフレームワークによって呼び出される、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|ポインターに入るかの境界から出たときに、フレームワークによって呼び出されます、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::OnKey](#onkey)|ユーザーが keytip を押したときに、フレームワークによって呼び出されますと`CMFCRibbonEdit`コントロールにフォーカスします。|  
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|更新するためにフレームワークによって呼び出されます、`CMFCRibbonEdit`ユーザーがコントロールでマウスの左ボタンを押したときを制御します。|  
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|更新するためにフレームワークによって呼び出される、`CMFCRibbonEdit`レイアウトの方向が変更された時点を制御します。|  
|[CMFCRibbonEdit::OnShow](#onshow)|表示または非表示にするためにフレームワークによって呼び出される、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::Redraw](#redraw)|表示を更新、`CMFCRibbonEdit`コントロール。|  
|[CMFCRibbonEdit::SetACCData](#setaccdata)|ユーザー補助データを設定、`CMFCRibbonEdit`オブジェクト。|  
|[CMFCRibbonEdit::SetEditText](#setedittext)|テキスト ボックスにテキストを設定します。|  
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|テキスト ボックスのテキストの配置を設定します。|  
|[CMFCRibbonEdit::SetWidth](#setwidth)|テキスト ボックスの幅を設定、`CMFCRibbonEdit`コントロール。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCRibbonEdit`オブジェクト、エディット コントロールの横にあるスピン ボタンの表示および編集コントロールのテキストを設定します。 このコード スニペットの一部である、 [MS Office 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonEdit.h  
  
##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched  
 示すかどうかの高さ、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールは、リボンの行の高さを縦に拡大できます。  
  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
  
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
 [入力] `nID`  
 コマンドの ID、`CMFCRibbonEdit`コントロール。  
  
 [入力] `nWidth`  
 幅 (ピクセル単位) のテキスト ボックス、`CMFCRibbonEdit`コントロール。  
  
 [入力] `lpszLabel`  
 ラベル、`CMFCRibbonEdit`コントロール。  
  
 [入力] `nImage`  
 使用する小さいイメージのインデックス、`CMFCRibbonEdit`コントロール。 小さいイメージのコレクションは、親のリボン カテゴリによって管理されます。  
  
### <a name="remarks"></a>コメント  
 `CMFCRibbonEdit`コントロールは大きなイメージを使用していません。  
  
##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom  
 指定した状態をコピー [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)現在オブジェクト[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
 ソース `CMFCRibbonEdit` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `src`パラメーター型でなければなりません`CMFCRibbonEdit`です。  
  
##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit  
 新しいテキスト ボックスを作成、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。  
  
```  
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,  
    DWORD dwEditStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクト。  
  
 [入力] `dwEditStyle`  
 テキスト ボックスのスタイルを指定します。 「解説」セクションに一覧表示ウィンドウのスタイルを組み合わせることができます、[コントロールのスタイルを編集](http://msdn.microsoft.com/library/windows/desktop/bb775464)Windows SDK に記載されていますいます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は、新しいテキスト ボックスへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 カスタム テキスト ボックスを作成する派生クラスでこのメソッドをオーバーライドします。  
  
 次を適用する[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)テキスト ボックスに。  
  
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
  
### <a name="remarks"></a>コメント  
  
##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList  
 ボックスの一覧を削除します。  
  
```  
virtual void DropDownList();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは何も行いません。 ドロップダウン リスト ボックスに、このメソッドをオーバーライドします。  
  
##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons  
 有効にし、テキスト ボックスのスピン ボタンの範囲を設定します。  
  
```  
void EnableSpinButtons(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMin`  
 スピン ボタンの最小値。  
  
 [入力] `nMax`  
 スピン ボタンの最大値。  
  
### <a name="remarks"></a>コメント  
 スピン ボタンは表示下矢印をクリックして、固定値のセット内を移動するユーザーを有効にします。  
  
##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize  
 コンパクト サイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。  
  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 コンパクト サイズ、`CMFCRibbonEdit`オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText  
 テキスト ボックス内のテキストを取得します。  
  
```  
CString GetEditText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキスト ボックス内のテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize  
 中間サイズを取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 中間サイズ、`CMFCRibbonEdit`オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign  
 テキスト ボックス内のテキストの配置を取得します。  
  
```  
int GetTextAlign() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキストの配置では、値を列挙します。 使用可能な値は、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 返される値では、次の編集コントロールのスタイルのいずれかです。  
  
- **ES_LEFT**左揃えの  
  
- **ES_CENTER**中央揃えの  
  
- **ES_RIGHT**右揃えの  
  
 これらのスタイルの詳細については、次を参照してください。[編集コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb775464)です。  
  
##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth  
 幅 (ピクセル単位) を取得、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
int GetWidth(BOOL bInFloatyMode = FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bInFloatyMode`  
 `TRUE` 場合、`CMFCRibbonEdit`コントロールがフローティング モードです。 それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 幅をピクセル単位での`CMFCRibbonEdit`コントロール。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode  
 示すための表示のサイズかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールは、コンパクトであることができます。  
  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドは常`TRUE`です。 表示サイズを最適化できるかどうかを示すためにこのメソッドをオーバーライドします。  
  
##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus  
 示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスします。  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合、`CMFCRibbonEdit`コントロールにフォーカスがあるそれ以外の`FALSE`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode  
 示しますのサイズを表示するかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが大きくなることができます。  
  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドは常`FALSE`です。 表示サイズが大きくなることがあるかどうかを示すためにこのメソッドをオーバーライドします。  
  
##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons  
 テキスト ボックスに、スピン ボタンがあるかどうかを示します。  
  
```  
virtual BOOL HasSpinButtons() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テキスト ボックスに、スピン ボタンがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted  
 示すかどうか、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールが強調表示されます。  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合、`CMFCRibbonEdit`コントロールは、それ以外の強調表示された`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect  
 フレームワークによって呼び出されますときに表示する四角形の寸法、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)変更を制御します。  
  
```  
virtual void OnAfterChangeRect(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw  
 描画するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage  
 ラベルを描画しのイメージに、フレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void OnDrawLabelAndImage(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList  
 描画するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コマンドのリスト ボックス内のコントロールです。  
  
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
 [入力] `pDC`  
 デバイス コンテキストへのポインター、`CMFCRibbonEdit`コントロール。  
  
 [入力] `strText`  
 表示テキスト[ ] (../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit クラス")です。  
  
 [入力] `nTextOffset`  
 (ピクセル単位) のテキストを表示するリスト ボックスの左側からの距離。  
  
 [入力] `rect`  
 表示する四角形、`CMFCRibbonEdit`コントロール。  
  
 [入力] `bIsSelected`  
 このパラメーターは使用されません。  
  
 [入力] `bHighlighted`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
 コマンドのリスト ボックスには、クイック アクセス ツールバーをカスタマイズするユーザーを有効にするリボン コントロールが表示されます。  
  
##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable  
 有効または無効にするためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void OnEnable(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` コントロールを有効にするには`FALSE`制御を無効にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight  
 ポインターに入るかの境界から出たときに、フレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void OnHighlight(BOOL bHighlight);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bHighlight`  
 `TRUE` 境界にポインターがある場合、`CMFCRibbonEdit`コントロール。 それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey  
 ユーザーが keytip を押したときに、フレームワークによって呼び出されますと[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロールにフォーカスします。  
  
```  
virtual BOOL OnKey(BOOL bIsMenuKey);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsMenuKey`  
 `TRUE` keytip がポップアップ メニューを表示する場合それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 イベントが処理された場合は、`TRUE`、それ以外の場合は、`FALSE`。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown  
 更新するためにフレームワークによって呼び出されます、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)ユーザーがコントロールでマウスの左ボタンを押したときを制御します。  
  
```  
virtual void OnLButtonDown(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp  
 ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnLButtonUp(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 このパラメーターは使用されません。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged  
 更新するためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)レイアウトの方向が変更された時点を制御します。  
  
```  
virtual void OnRTLChanged(BOOL bIsRTL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bIsRTL`  
 `TRUE` レイアウトが右から左の場合`FALSE`レイアウトが左から右への場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow  
 表示または非表示にするためにフレームワークによって呼び出される、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 `TRUE` コントロールを表示するには`FALSE`コントロールを非表示にします。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw  
 表示を更新、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
virtual void Redraw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを表示する四角形を再描画、`CMFCRibbonEdit`オブジェクトを直接呼び出していない[CWnd::RedrawWindow](http://msdn.microsoft.com/library/windows/desktop/dd162911)で、 `RDW_INVALIDATE`、 `RDW_ERASE`、および`RDW_UPDATENOW`フラグを設定します。  
  
##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData  
 ユーザー補助データを設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)オブジェクト。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 親ウィンドウへのポインター、`CMFCRibbonEdit`オブジェクト。  
  
 `data`  
 アクセシビリティ データを`CMFCRibbonEdit`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText  
 テキスト ボックスにテキストを設定します。  
  
```  
void SetEditText(CString strText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strText`  
 テキスト ボックスのテキストです。  
  
##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign  
 テキスト ボックスのテキストの配置を設定します。  
  
```  
void SetTextAlign(int nAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nAlign`  
 テキストの配置では、値を列挙します。 使用可能な値は、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 パラメーター`nAlign`コントロールのスタイルは、次の編集の 1 つ。  
  
- **ES_LEFT**左揃えの  
  
- **ES_CENTER**中央揃えの  
  
- **ES_RIGHT**右揃えの  
  
 これらのスタイルの詳細については、次を参照してください。[編集コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb775464)です。  
  
##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth  
 テキスト ボックスの幅を設定、 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)コントロール。  
  
```  
void SetWidth(
    int nWidth,  
    BOOL bInFloatyMode = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nWidth`  
 テキスト ボックスのピクセル単位の幅。  
  
 `bInFloatyMode`  
 `TRUE` 浮動小数点モードの幅を設定するには`FALSE`通常モードの幅を設定します。  
  
### <a name="remarks"></a>コメント  
 `CMFCRibbonEdit`コントロールの表示モードに応じて 2 分の幅がある: 浮動モードと通常モードです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)