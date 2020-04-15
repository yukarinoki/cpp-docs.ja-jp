---
title: クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: f51c1b75e0c096a34b190e36e097aaca4109b5f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367581"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>クラス

クラス`CMFCDesktopAlertWndInfo`は、クラスで使用[されます](../../mfc/reference/cmfcdesktopalertwnd-class.md)。 デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の操作を行います。](#operator_eq)||

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[を設定します m_hIcon。](#m_hicon)|表示されるアイコンへのハンドル。|
|[をクリックします m_nURLCmdID。](#m_nurlcmdid)|デスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID。|
|[を設定します m_strText。](#m_strtext)|デスクトップ通知ウィンドウに表示されるテキスト。|
|[を設定します m_strURL。](#m_strurl)|デスクトップ通知ウィンドウに表示されるリンク。|

## <a name="remarks"></a>解説

クラス`CMFCDesktopAlertWndInfo`は、デスクトップ警告ウィンドウの既定のダイアログに表示される要素を指定するメソッドを指定する[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)メソッドに渡されます。 既定のダイアログ には、次の 3 つの項目を含めることができます。

- アイコンは[、m_hIcon 呼](#m_hicon)び出すことによって設定されます。

- ラベルまたはテキスト メッセージは[、CMFCDesktopAlertWndInfo::m_strText](#m_strtext)を呼び出すことによって設定されます。

- リンクは[、m_strURL 呼](#m_strurl)び出すことによって設定されます。 リンクがクリックされたときに実行されるコマンドを設定するには[、CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)呼び出します。

既定のダイアログ ボックスが十分でない場合は、カスタム ダイアログを作成し、このクラスを使用する代わりに[CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)メソッドに渡すことができます。 詳細については、「[クラス」](../../mfc/reference/cmfcdesktopalertdialog-class.md)を参照してください。

## <a name="example"></a>例

クラスのさまざまなメンバーを使用する方法を次の例に`CMFCDesktopAlertWndInfo`示します。 この例では、表示されるアイコン、デスクトップ通知ウィンドウに表示されるテキスト、デスクトップ通知ウィンドウに表示されるリンク、およびデスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID にハンドルを設定する方法を示します。 この例は[デスクトップ警告デモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx デスクトップ アラート ダイアログ.h

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>次の操作を行います。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>パラメーター

[in]*src*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a>を設定します m_hIcon。

表示されるアイコンへのハンドル。

```
HICON m_hIcon;
```

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a>をクリックします m_nURLCmdID。

デスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID。

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>解説

コマンド ID は、ユーザーが[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)で指定されたリンクをクリックすると、ポップアップ ウィンドウの所有者に送信されます。

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a>を設定します m_strText。

デスクトップ通知ウィンドウに表示されるテキスト。

```
CString m_strText;
```

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a>を設定します m_strURL。

デスクトップ通知ウィンドウに表示されるリンク。

```
CString m_strURL;
```

### <a name="remarks"></a>解説

ユーザーがリンクをクリックすると[、CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)コマンド ID を持つコマンドがポップアップ ウィンドウの所有者に送信されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd Class](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[をクリックします。](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
