---
title: CUserTool クラス
ms.date: 11/04/2016
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
ms.openlocfilehash: 183b30961e4a7d3079fa0d035a4ddc38bc2eebac
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752022"
---
# <a name="cusertool-class"></a>CUserTool クラス

ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 [**カスタマイズ**] ダイアログ ボックスの [**ツール**] タブ ( [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) を使用すると、ユーザー ツールを追加したり、各ユーザー ツールの名前、コマンド、引数、および初期ディレクトリを指定したりできます。

## <a name="syntax"></a>構文

```
class CUserTool : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CUserTool::コピーアイコンクリップボードへ](#copyicontoclipboard)||
|[CUserTool::Dローツールアイコン](#drawtoolicon)|指定された四角形にユーザー ツール アイコンを描画します。|
|[CUserTool::ゲットコマンド](#getcommand)|ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。|
|[をクリックします。](#getcommandid)|ユーザー ツールのメニュー項目のコマンド ID を返します。|
|[呼び出し](#invoke)|ユーザー ツールに関連付けられているコマンドを実行します。|
|[CUserTool::シリアライズ](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|
|[CUserTool::セットコマンド](#setcommand)|ユーザー ツールに関連付けられているコマンドを設定します。|
|[CUserTool::セットツールアイコン](#settoolicon)|ツールに関連付けられているアプリケーションからユーザー ツールのアイコンを読み込みます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CUser ツール::ロードデフォルトアイコン](#loaddefaulticon)|ユーザー ツールの既定のアイコンを読み込みます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CUserTool::m_strArguments](#m_strarguments)|ユーザー ツールのコマンド ライン引数。|
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|ユーザー ツールの初期ディレクトリ。|
|[CUserTool::m_strLabel](#m_strlabel)|ツールのメニュー項目に表示されるツール名。|

## <a name="remarks"></a>解説

アプリケーションでユーザー ツールを有効にする方法の詳細については、「 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)」を参照してください。

## <a name="example"></a>例

次の例は、`CUserToolsManager`オブジェクトからツールを作成し、メンバー変数を`m_strLabel`設定し、ユーザー ツールが実行するアプリケーションを設定する方法を示しています。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CUserTool](../../mfc/reference/cusertool-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxusertool.h

## <a name="cusertoolcopyicontoclipboard"></a><a name="copyicontoclipboard"></a>CUserTool::コピーアイコンクリップボードへ

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
BOOL CopyIconToClipboard();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cusertooldrawtoolicon"></a><a name="drawtoolicon"></a>CUserTool::Dローツールアイコン

指定された四角形の中心にユーザー ツール アイコンを描画します。

```cpp
void DrawToolIcon(
    CDC* pDC,
    const CRect& rectImage);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトイメージ*<br/>
[in]アイコンを表示する領域の座標を指定します。

## <a name="cusertoolgetcommand"></a><a name="getcommand"></a>CUserTool::ゲットコマンド

ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。

```
const CString& GetCommand() const;
```

### <a name="return-value"></a>戻り値

ユーザー ツール`CString`に関連付けられているコマンドのテキストを含むオブジェクトへの参照。

## <a name="cusertoolgetcommandid"></a><a name="getcommandid"></a>をクリックします。

ユーザー ツールのコマンド ID を返します。

```
UINT GetCommandId() const;
```

### <a name="return-value"></a>戻り値

このユーザー ツールのコマンド ID。

## <a name="cusertoolinvoke"></a><a name="invoke"></a>呼び出し

ユーザー ツールに関連付けられているコマンドを実行します。

```
virtual BOOL Invoke();
```

### <a name="return-value"></a>戻り値

コマンドが正常に実行された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

[ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew)を呼び出して、ユーザー ツールに関連付けられたコマンドを実行します。 コマンドが空の場合、または[ShellExecute](/windows/win32/api/shellapi/nf-shellapi-shellexecutew)が失敗した場合、この関数は失敗します。

## <a name="cusertoolloaddefaulticon"></a><a name="loaddefaulticon"></a>CUser ツール::ロードデフォルトアイコン

ユーザー ツールの既定のアイコンを読み込みます。

```
virtual HICON LoadDefaultIcon();
```

### <a name="return-value"></a>戻り値

読み込まれたアイコン (HICON) へのハンドル。

### <a name="remarks"></a>解説

フレームワークは、ツールの実行可能ファイルからユーザー定義ツールのアイコンを読み込めない場合に、このメソッドを呼び出します。

独自の既定のツール アイコンを指定するには、このメソッドをオーバーライドします。

## <a name="cusertoolm_strarguments"></a><a name="m_strarguments"></a>CUserTool::m_strArguments

ユーザー ツールのコマンド ライン引数。

```
CString m_strArguments;
```

### <a name="remarks"></a>解説

この文字列は[、CUserTool::Invoke](#invoke)を呼び出すか、ユーザーがこのツールに関連付けられているコマンドをクリックしたときにツールに渡されます。

## <a name="cusertoolm_strinitialdirectory"></a><a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory

ユーザー ツールの初期ディレクトリを指定します。

```
CString m_strInitialDirectory;
```

### <a name="remarks"></a>解説

この変数は[、CUserTool::Invoke](#invoke)を呼び出したとき、またはユーザーがこのツールに関連付けられたコマンドをクリックしたときにツールが実行する初期ディレクトリを指定します。

## <a name="cusertoolm_strlabel"></a><a name="m_strlabel"></a>CUserTool::m_strLabel

ツールのメニュー項目に表示されるラベル。

```
CString m_strLabel;
```

## <a name="cusertoolserialize"></a><a name="serialize"></a>CUserTool::シリアライズ

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

[in]*ar*<br/>

### <a name="remarks"></a>解説

## <a name="cusertoolsetcommand"></a><a name="setcommand"></a>CUserTool::セットコマンド

ユーザー ツールが実行するアプリケーションを設定します。

```cpp
void SetCommand(LPCTSTR lpszCmd);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ユーザー ツールに関連付ける新しいアプリケーションを指定します。

### <a name="remarks"></a>解説

ユーザー ツールで実行する新しいアプリケーションを設定します。 このメソッドは、古いアイコンを破棄し、指定されたアプリケーションから新しいアイコンを読み込みます。 アプリケーションからアイコンを読み込むことができない場合は[、CUserTool::LoadDefaultIcon](#loaddefaulticon)を呼び出してユーザー ツールの既定のアイコンを読み込みます。

## <a name="cusertoolsettoolicon"></a><a name="settoolicon"></a>CUserTool::セットツールアイコン

ツールが使用するアプリケーションからユーザー ツールのアイコンを読み込みます。

```
virtual HICON SetToolIcon();
```

### <a name="return-value"></a>戻り値

読み込まれたアイコンへのハンドル。

### <a name="remarks"></a>解説

メニュー項目に表示されるアイコンを読み込みます。 このメソッドは、ツールが使用する実行可能ファイル内のアイコンを検索します。 既定のアイコンがない場合は、代わりに[CUserTool::LoadDefaultIcon](#loaddefaulticon)によって提供されるアイコンが使用されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[クラス](../../mfc/reference/cusertoolsmanager-class.md)
