---
title: CWinFormsDialog クラス
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: 3772033df59e065cedca61012cd479c812cf5b66
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367426"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog クラス

Windows フォーム ユーザー コントロールをホストする MFC ダイアログ クラスのラッパーです。

## <a name="syntax"></a>構文

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>パラメーター

*コントロール制御*<br/>
MFC アプリケーションに表示される .NET Framework ユーザー コントロール。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::CWinFormsダイアログ](#cwinformsdialog)|`CWinFormsDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::コントロールを取得します。](#getcontrol)|Windows フォーム ユーザー コントロールへの参照を取得します。|
|[ダイアログボックス::コントロールハンドルを取得します。](#getcontrolhandle)|Windows フォーム ユーザー コントロールへのウィンドウ ハンドルを取得します。|
|[ダイアログ::オンイニトダイアログ](#oninitdialog)|MFC ダイアログ ボックスを初期化するには、そのダイアログ ボックスに Windows フォーム ユーザー コントロールを作成してホストします。|

### <a name="public-operators"></a>パブリック演算子

|名前||
|----------|-|
|[ダイアログ::演算子 -&gt;](#operator_-_gt)|式の[中で CWinForms ダイアログを](#getcontrol)置き換えます。|
|[コントロールの操作を行います。](#operator-tmanagedcontrol-hat)|型を Windows フォーム ユーザー コントロールへの参照としてキャストします。|

## <a name="remarks"></a>解説

`CWinFormsDialog`は、Windows フォーム のユーザー コントロールをホストする MFC ダイアログ クラス ( [CDialog](../../mfc/reference/cdialog-class.md)) のラッパーです。 これにより、.NET Framework コントロールをモーダルまたはモードレスの MFC ダイアログ ボックスに表示できます。

Windows フォームの使用方法の詳細については[、「MFC で Windows フォーム ユーザー コントロールを使用する](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」および[「MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwinforms.h

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a>ダイアログボックス::CWinFormsダイアログ

`CWinFormsDialog` オブジェクトを構築します。

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
ダイアログ ボックス テンプレート リソースの ID を格納します。 ダイアログ エディターを使用してダイアログ テンプレートを作成し、アプリケーションのリソース スクリプト ファイルに格納します。 ダイアログ テンプレートの詳細については、「 [CDialog クラス](../../mfc/reference/cdialog-class.md)」を参照してください。

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a>ダイアログボックス::コントロールを取得します。

Windows フォーム ユーザー コントロールへの参照を取得します。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>戻り値

MFC ダイアログ ボックスの Windows フォーム コントロールへの参照を返します。

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a>ダイアログボックス::コントロールハンドルを取得します。

Windows フォーム ユーザー コントロールへのウィンドウ ハンドルを取得します。

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>戻り値

Windows フォーム ユーザー コントロールへのウィンドウ ハンドルを返します。

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a>ダイアログ::オンイニトダイアログ

MFC ダイアログ ボックスを初期化するには、そのダイアログ ボックスに Windows フォーム ユーザー コントロールを作成してホストします。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

アプリケーションが入力フォーカスをダイアログ ボックスのコントロールのいずれかに設定したかどうかを指定するブール値。 0`OnInitDialog`以外の値を返す場合、ダイアログ ボックスの最初のコントロールに入力フォーカスが設定されます。 このメソッドは、アプリケーションがダイアログ ボックスのコントロールのいずれかに入力フォーカスを明示的に設定している場合にのみ 0 を返すことができます。

### <a name="remarks"></a>解説

作成、[作成](../../mfc/reference/cdialog-class.md#create)、[間接](../../mfc/reference/cdialog-class.md#createindirect)作成、または[CDialog](../../mfc/reference/cdialog-class.md)から継承された[DoModal](../../mfc/reference/cdialog-class.md#domodal)メソッドを使用して、MFC ダイアログ ボックスが作成されると、WM_INITDIALOGメッセージが送信され、このメソッドが呼び出されます。 ダイアログ ボックスに Windows フォーム コントロールのインスタンスを作成し、ユーザー コントロールのサイズに合わせてダイアログ ボックスのサイズを調整します。 次に、MFC ダイアログ ボックスで新しいコントロールをホストします。

ダイアログ ボックスの初期化時に特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 このメソッドの使用方法の詳細については[、「CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)」を参照してください。

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a>ダイアログ::演算子 -&gt;

式の[中で CWinForms ダイアログを](#getcontrol)置き換えます。

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>解説

この演算子は、式内で置き`GetControl`換える便利な構文を提供します。

Windows フォームの使用方法については[、「MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a>コントロールの操作を行います。

型を Windows フォーム ユーザー コントロールへの参照としてキャストします。

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>解説

この演算子は、Windows フォーム コントロールへの参照として型をキャストします。 Windows フォーム のユーザー`CWinFormsDialog<TManagedControl>`コントロール オブジェクトへのポインターを受け取る関数にダイアログ ボックスを渡すために使用されます。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)
