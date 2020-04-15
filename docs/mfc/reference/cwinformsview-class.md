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
ms.openlocfilehash: 6eb6b9e385e9dbc96eb3b62ffb80909e54569e97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369606"
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
|[ビュー::CWinフォームビュー](#cwinformsview)|`CWinFormsView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ビュー::コントロールを取得します。](#getcontrol)|Windows フォーム コントロールへのポインターを取得します。|

### <a name="public-operators"></a>パブリック演算子

|名前||
|----------|-|
|[コントロール^](#operator_control)|型を Windows フォーム コントロールへのポインターとしてキャストします。|

## <a name="remarks"></a>解説

MFC では`CWinFormsView`、クラスを使用して、MFC ビュー内で .NET Framework Windows フォーム コントロールをホストします。 コントロールはネイティブ ビューの子で、MFC ビューのクライアント領域全体を占めます。 結果は`CFormView`ビューに似ており、Windows フォーム デザイナーと実行時にリッチ フォーム ベースのビューを作成できます。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

> [!NOTE]
> MFC Windows フォームの統合は、MFC (AFXDLL が定義されているプロジェクト) と動的にリンクするプロジェクトでのみ機能します。

> [!NOTE]
> MFC スプリッター ウィンドウ ([クラスの分割](../../mfc/reference/csplitterwnd-class.md)) をサポートしていません。 現在、Windows フォーム 分割コントロールのみがサポートされています。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h

## <a name="cwinformsviewcwinformsview"></a><a name="cwinformsview"></a>ビュー::CWinフォームビュー

`CWinFormsView` オブジェクトを構築します。

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>パラメーター

*型指定*<br/>
Windows フォーム ユーザー コントロールのデータ型へのポインター。

### <a name="example"></a>例

次の例では、クラス`CUserView`は、コンストラクターから`CWinFormsView`継承し、の型`UserControl1`をコンストラクターに`CWinFormsView`渡します。 `UserControl1`は、コントロールライブラリ1.dll のカスタムビルドコントロールです。

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

## <a name="cwinformsviewgetcontrol"></a><a name="getcontrol"></a>ビュー::コントロールを取得します。

Windows フォーム コントロールへのポインターを取得します。

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>戻り値

`System.Windows.Forms.Control` オブジェクトを指すポインターです。

### <a name="remarks"></a>解説

Windows フォームの使用方法の例については[、「MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformsviewoperator-control"></a><a name="operator_control"></a>コントロール^

型を Windows フォーム コントロールへのポインターとしてキャストします。

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>解説

この演算子を使用すると、型`CWinFormsView`の Windows フォーム コントロールへのポインターを受け取る<xref:System.Windows.Forms.Control>関数にビューを渡すことができます。

### <a name="example"></a>例

  [を](#getcontrol)参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl クラス](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog クラス](../../mfc/reference/cwinformsdialog-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cformview-class.md)
