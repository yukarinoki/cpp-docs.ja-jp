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
ms.openlocfilehash: f4a5e6b88527dad8606092ccebd4899bba5181f6
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426289"
---
# <a name="cwinformsview-class"></a>CWinFormsView クラス

Windows フォーム コントロールのホスティング用の汎用機能を MFC ビューとして提供します。

## <a name="syntax"></a>構文

```
class CWinFormsView : public CView;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CWinFormsView:: CWinFormsView](#cwinformsview)|`CWinFormsView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CWinFormsView:: GetControl](#getcontrol)|Windows フォームコントロールへのポインターを取得します。|

### <a name="public-operators"></a>パブリック演算子

|Name||
|----------|-|
|[CWinFormsView:: operator コントロール ^](#operator_control)|型を Windows フォームコントロールへのポインターとしてキャストします。|

## <a name="remarks"></a>解説

MFC では、`CWinFormsView` クラスを使用して、MFC ビュー内の .NET Framework Windows フォームコントロールをホストします。 コントロールはネイティブビューの子であり、MFC ビューのクライアント領域全体を占有します。 結果は `CFormView` ビューに似ており、Windows フォームデザイナーと実行時間を利用して、豊富なフォームベースのビューを作成できます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

> [!NOTE]
>  MFC Windows フォーム統合は、MFC と動的にリンクするプロジェクト (AFXDLL が定義されているプロジェクト) でのみ機能します。

> [!NOTE]
>  CWinFormsView は MFC スプリッターウィンドウ ( [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)) をサポートしていません。 現時点では、Windows フォームスプリッターコントロールのみがサポートされています。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms

##  <a name="cwinformsview"></a>CWinFormsView:: CWinFormsView

`CWinFormsView` オブジェクトを構築します。

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>パラメーター

*pManagedViewType*<br/>
Windows フォームユーザーコントロールのデータ型へのポインター。

### <a name="example"></a>例

次の例では、`CUserView` クラスは `CWinFormsView` から継承し、`UserControl1` の型を `CWinFormsView` コンストラクターに渡します。 `UserControl1` は、ControlLibrary1 のカスタムビルドコントロールです。

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

##  <a name="getcontrol"></a>CWinFormsView:: GetControl

Windows フォームコントロールへのポインターを取得します。

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>戻り値

`System.Windows.Forms.Control` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

Windows フォームの使用方法の例については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

##  <a name="operator_control"></a>CWinFormsView:: operator コントロール ^

型を Windows フォームコントロールへのポインターとしてキャストします。

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>解説

この演算子を使用すると、<xref:System.Windows.Forms.Control>型の Windows フォームコントロールへのポインターを受け取る関数に `CWinFormsView` ビューを渡すことができます。

### <a name="example"></a>例

  「 [CWinFormsView:: GetControl](#getcontrol)」を参照してください。

## <a name="see-also"></a>参照

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl クラス](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)
