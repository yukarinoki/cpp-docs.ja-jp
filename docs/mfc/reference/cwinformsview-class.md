---
title: CWinFormsView クラス
ms.date: 11/04/2016
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
ms.openlocfilehash: 3c247babd2ec1057f1e24b8132ed81727a0fd402
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040653"
---
# <a name="cwinformsview-class"></a>CWinFormsView クラス

Windows フォーム コントロールのホスティング用の汎用機能を MFC ビューとして提供します。

## <a name="syntax"></a>構文

```
class CWinFormsView : public CView;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinFormsView:: CWinFormsView](#cwinformsview)|`CWinFormsView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinFormsView:: GetControl](#getcontrol)|Windows フォームコントロールへのポインターを取得します。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-|
|[CWinFormsView:: operator コントロール ^](#operator_control)|型を Windows フォームコントロールへのポインターとしてキャストします。|

## <a name="remarks"></a>注釈

MFC では、クラスを使用して、 `CWinFormsView` mfc ビュー内の .NET Framework Windows フォームコントロールをホストします。 コントロールはネイティブビューの子であり、MFC ビューのクライアント領域全体を占有します。 結果はビューに似ているため `CFormView` 、Windows フォームデザイナーと実行時間を利用して、豊富なフォームベースのビューを作成することができます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

> [!NOTE]
> MFC Windows フォーム統合は、MFC と動的にリンクするプロジェクト (AFXDLL が定義されているプロジェクト) でのみ機能します。

> [!NOTE]
> CWinFormsView は MFC スプリッターウィンドウ ( [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)) をサポートしていません。 現時点では、Windows フォームスプリッターコントロールのみがサポートされています。

## <a name="requirements"></a>要件

**ヘッダー:** afxwinforms

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a> CWinFormsView:: CWinFormsView

`CWinFormsView` オブジェクトを構築します。

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>パラメーター

*pManagedViewType*<br/>
Windows フォームユーザーコントロールのデータ型へのポインター。

### <a name="example"></a>例

次の例では、 `CUserView` クラスはから継承 `CWinFormsView` し、の型を `UserControl1` コンストラクターに渡し `CWinFormsView` ます。 `UserControl1` は ControlLibrary1.dll のカスタムビルドコントロールです。

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a> CWinFormsView:: GetControl

Windows フォームコントロールへのポインターを取得します。

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>戻り値

`System.Windows.Forms.Control` オブジェクトを指すポインターです。

### <a name="remarks"></a>注釈

Windows フォームの使用方法の例については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a> CWinFormsView:: operator コントロール ^

型を Windows フォームコントロールへのポインターとしてキャストします。

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>注釈

この演算子を使用すると、 `CWinFormsView` 型の Windows フォームコントロールへのポインターを受け取る関数にビューを渡すことができ <xref:System.Windows.Forms.Control> ます。

### <a name="example"></a>例

  「 [CWinFormsView:: GetControl](#getcontrol)」を参照してください。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl クラス](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)
