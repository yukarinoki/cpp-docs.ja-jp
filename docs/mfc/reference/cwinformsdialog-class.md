---
description: '詳細情報: CWinFormsDialog クラス'
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
ms.openlocfilehash: 501f9c354bd6f0b7a628aabb93f4680155f74a69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342622"
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

*TManagedControl*<br/>
MFC アプリケーションに表示される .NET Framework ユーザーコントロール。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinFormsDialog:: CWinFormsDialog](#cwinformsdialog)|`CWinFormsDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinFormsDialog:: GetControl](#getcontrol)|Windows フォームユーザーコントロールへの参照を取得します。|
|[CWinFormsDialog:: GetControlHandle](#getcontrolhandle)|Windows フォームユーザーコントロールへのウィンドウハンドルを取得します。|
|[CWinFormsDialog:: OnInitDialog](#oninitdialog)|Windows フォームユーザーコントロールを作成してホストすることで、MFC ダイアログボックスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-|
|[CWinFormsDialog:: operator-&gt;](#operator_-_gt)|式の [CWinFormsDialog:: GetControl](#getcontrol) を置き換えます。|
|[CWinFormsDialog:: operator TManagedControl ^](#operator-tmanagedcontrol-hat)|型を Windows フォームユーザーコントロールへの参照としてキャストします。|

## <a name="remarks"></a>解説

`CWinFormsDialog` は、Windows フォームユーザーコントロールをホストする MFC ダイアログクラス ( [CDialog](../../mfc/reference/cdialog-class.md)) のラッパーです。 これにより、モーダルまたはモードレスの MFC ダイアログボックスに .NET Framework コントロールを表示できます。

Windows フォームの使用方法の詳細については、「mfc [での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 」および「 [mfc ダイアログボックスとしての Windows フォームユーザーコントロールのホスト](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** afxwinforms

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a> CWinFormsDialog:: CWinFormsDialog

`CWinFormsDialog` オブジェクトを構築します。

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>パラメーター

*nIDTemplate*<br/>
ダイアログボックステンプレートリソースの ID を格納します。 ダイアログエディターを使用してダイアログテンプレートを作成し、アプリケーションのリソーススクリプトファイルに保存します。 ダイアログテンプレートの詳細については、「 [CDialog クラス](../../mfc/reference/cdialog-class.md)」を参照してください。

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a> CWinFormsDialog:: GetControl

Windows フォームユーザーコントロールへの参照を取得します。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>戻り値

MFC ダイアログボックス内の Windows フォームコントロールへの参照を返します。

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a> CWinFormsDialog:: GetControlHandle

Windows フォームユーザーコントロールへのウィンドウハンドルを取得します。

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>戻り値

Windows フォームユーザーコントロールへのウィンドウハンドルを返します。

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a> CWinFormsDialog:: OnInitDialog

Windows フォームユーザーコントロールを作成してホストすることで、MFC ダイアログボックスを初期化します。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

アプリケーションがダイアログボックスのコントロールのいずれかに入力フォーカスを設定したかどうかを指定するブール値です。 が `OnInitDialog` 0 以外の値を返した場合、Windows はダイアログボックスの最初のコントロールに入力フォーカスを設定します。 このメソッドは、アプリケーションがダイアログボックス内のコントロールのいずれかに入力フォーカスを明示的に設定している場合にのみ、0を返すことができます。

### <a name="remarks"></a>解説

MFC ダイアログボックスが作成されると ([[作成](../../mfc/reference/cdialog-class.md#create)]、[ [createindirect](../../mfc/reference/cdialog-class.md#createindirect)]、または [DoModal [] から継承](../../mfc/reference/cdialog-class.md)された[DoModal](../../mfc/reference/cdialog-class.md#domodal)メソッドを使用)、WM_INITDIALOG メッセージが送信され、このメソッドが呼び出されます。 このメソッドは、ダイアログボックスに Windows フォームコントロールのインスタンスを作成し、ユーザーコントロールのサイズに合わせてダイアログボックスのサイズを調整します。 次に、MFC ダイアログボックスで新しいコントロールをホストします。

ダイアログボックスが初期化されるときに特別な処理を実行する必要がある場合は、このメンバー関数をオーバーライドします。 このメソッドの使用方法の詳細については、「 [CDialog:: OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)」を参照してください。

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a> CWinFormsDialog:: operator-&gt;

式の [CWinFormsDialog:: GetControl](#getcontrol) を置き換えます。

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>解説

この演算子は、式で置き換えられる便利な構文を提供 `GetControl` します。

Windows フォームの使用方法の詳細については、「 [MFC での Windows フォームユーザーコントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a> CWinFormsDialog:: operator TManagedControl ^

型を Windows フォームユーザーコントロールへの参照としてキャストします。

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>解説

この演算子は、型を Windows フォームコントロールへの参照としてキャストします。 これは、 `CWinFormsDialog<TManagedControl>` Windows フォームユーザーコントロールオブジェクトへのポインターを受け取る関数にダイアログボックスを渡すために使用されます。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
