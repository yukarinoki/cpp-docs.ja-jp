---
description: '詳細情報: CMFCDesktopAlertWndInfo クラス'
title: CMFCDesktopAlertWndInfo クラス
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
ms.openlocfilehash: 1c23e5b890e892df9bccce51542f2d36b3d6f7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250687"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo クラス

`CMFCDesktopAlertWndInfo`クラスは、 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)と共に使用されます。 デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。

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
|[CMFCDesktopAlertWndInfo:: operator =](#operator_eq)||

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo:: m_hIcon](#m_hicon)|表示されるアイコンへのハンドル。|
|[CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid)|デスクトップの [警告] ウィンドウのリンクに関連付けられているコマンド ID。|
|[CMFCDesktopAlertWndInfo:: m_strText](#m_strtext)|デスクトップの [警告] ウィンドウに表示されるテキスト。|
|[CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl)|デスクトップの [アラート] ウィンドウに表示されるリンク。|

## <a name="remarks"></a>解説

クラスは、 `CMFCDesktopAlertWndInfo` [CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) メソッドに渡され、デスクトップの [警告] ウィンドウの既定のダイアログに表示される要素を指定します。 既定のダイアログには、次の3つの項目を含めることができます。

- [CMFCDesktopAlertWndInfo:: m_hIcon](#m_hicon)を呼び出すことによって設定されるアイコン。

- ラベル (テキストメッセージ)。 [CMFCDesktopAlertWndInfo:: m_strText](#m_strtext)を呼び出すことによって設定されます。

- [CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl)を呼び出すことによって設定されるリンク。 リンクがクリックされたときに実行されるコマンドを設定するには、 [CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid)を呼び出します。

既定のダイアログでは不十分な場合は、カスタムダイアログを作成し、このクラスを使用する代わりに [CMFCDesktopAlertWnd:: create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) メソッドに渡すことができます。 詳細については、「 [Cmfcdesktopalertdialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)」を参照してください。

## <a name="example"></a>例

クラスのさまざまなメンバーを使用する方法を次の例に示し `CMFCDesktopAlertWndInfo` ます。 この例では、表示されるアイコン、デスクトップの [アラート] ウィンドウに表示されるテキスト、デスクトップの [警告] ウィンドウに表示されるリンク、およびデスクトップの [警告] ウィンドウのリンクに関連付けられているコマンド ID にハンドルを設定する方法を示します。 この例は、 [デスクトップアラートのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDesktopAlertDialog

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a> CMFCDesktopAlertWndInfo:: operator =

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>パラメーター

から *src*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a> CMFCDesktopAlertWndInfo:: m_hIcon

表示されるアイコンへのハンドル。

```
HICON m_hIcon;
```

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a> CMFCDesktopAlertWndInfo:: m_nURLCmdID

デスクトップの [警告] ウィンドウのリンクに関連付けられているコマンド ID。

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>解説

コマンド ID は、ユーザーが [CMFCDesktopAlertWndInfo:: m_strURL](#m_strurl)によって指定されたリンクをクリックすると、ポップアップウィンドウの所有者に送信されます。

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a> CMFCDesktopAlertWndInfo:: m_strText

デスクトップの [警告] ウィンドウに表示されるテキスト。

```
CString m_strText;
```

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a> CMFCDesktopAlertWndInfo:: m_strURL

デスクトップの [アラート] ウィンドウに表示されるリンク。

```
CString m_strURL;
```

### <a name="remarks"></a>解説

ユーザーがリンクをクリックすると、 [CMFCDesktopAlertWndInfo:: m_nURLCmdID](#m_nurlcmdid) コマンド ID を持つコマンドがポップアップウィンドウの所有者に送信されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd:: Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)
