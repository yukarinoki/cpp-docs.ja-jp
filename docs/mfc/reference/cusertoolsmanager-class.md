---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
helpviewer_keywords:
- CUserToolsManager [MFC], CUserToolsManager
- CUserToolsManager [MFC], CreateNewTool
- CUserToolsManager [MFC], FindTool
- CUserToolsManager [MFC], GetArgumentsMenuID
- CUserToolsManager [MFC], GetDefExt
- CUserToolsManager [MFC], GetFilter
- CUserToolsManager [MFC], GetInitialDirMenuID
- CUserToolsManager [MFC], GetMaxTools
- CUserToolsManager [MFC], GetToolsEntryCmd
- CUserToolsManager [MFC], GetUserTools
- CUserToolsManager [MFC], InvokeTool
- CUserToolsManager [MFC], IsUserToolCmd
- CUserToolsManager [MFC], LoadState
- CUserToolsManager [MFC], MoveToolDown
- CUserToolsManager [MFC], MoveToolUp
- CUserToolsManager [MFC], RemoveTool
- CUserToolsManager [MFC], SaveState
- CUserToolsManager [MFC], SetDefExt
- CUserToolsManager [MFC], SetFilter
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
ms.openlocfilehash: 1e9be5d7cb81f2769b98d9baeae786873f5fa73d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751981"
---
# <a name="cusertoolsmanager-class"></a>クラス

アプリケーション内の[CUserTool クラス](../../mfc/reference/cusertool-class.md)オブジェクトのコレクションを保持します。 ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 `CUserToolsManager` オブジェクトは、ユーザーまたは開発者がアプリケーションに新しいユーザー ツールを追加できるようにします。 ユーザー ツールに関連するコマンドの実行をサポートし、Windows レジストリにユーザー ツールに関する情報を保存します。

## <a name="syntax"></a>構文

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CUser ツールマネージャー::CUser ツールマネージャー](#cusertoolsmanager)|`CUserToolsManager` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CUser ツールマネージャー::新しいツールの作成](#createnewtool)|新しいユーザー ツールを作成します。|
|[ツールマネージャー::ツールを検索](#findtool)|指定したコマンド ID`CMFCUserTool`に関連付けられているオブジェクトへのポインターを返します。|
|[ツールマネージャー::引数メニューID](#getargumentsmenuid)|[**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[引数]** メニューに関連付けられているリソース ID を返します。|
|[CUser ツールマネージャー::ゲットデフエクスク](#getdefext)|[**ファイルを開く**] ダイアログ ボックス[(CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) が [**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用する既定の拡張子を返します。|
|[コントロール::ゲットフィルター](#getfilter)|[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用するファイル フィルタを返します。|
|[をクリックします。](#getinitialdirmenuid)|[**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[初期ディレクトリ**] メニューに関連付けられているリソース ID を返します。|
|[CUser ツールマネージャー::ゲットマックスツール](#getmaxtools)|アプリケーションに割り当てることができるユーザー ツールの最大数を返します。|
|[ツールマネージャー::ツールエントリCmd](#gettoolsentrycmd)|ユーザー ツールのメニュー項目プレースホルダーのコマンド ID を返します。|
|[ツールマネージャー::ユーザーツール](#getusertools)|ユーザー ツールの一覧への参照を返します。|
|[ツールマネージャー::ツールを呼び出します](#invoketool)|指定したコマンド ID を持つユーザー ツールに関連付けられているアプリケーションを実行します。|
|[ツールマネージャー::IsUserツールCmd](#isusertoolcmd)|コマンド ID がユーザー ツールに関連付けられているかどうかを判断します。|
|[CUser ツールマネージャー::ロードステート](#loadstate)|Windows レジストリからユーザー ツールに関する情報を読み込みます。|
|[CUserツールマネージャー::ツールダウンの移動](#movetooldown)|指定したユーザー ツールをユーザー ツールの一覧の下に移動します。|
|[CUserツールマネージャー::ムーブツールアップ](#movetoolup)|指定したユーザー ツールをユーザー ツールの一覧の上に移動します。|
|[ツールマネージャー::ツールの削除](#removetool)|指定したユーザー ツールをアプリケーションから削除します。|
|[CUser ツールマネージャー::セーブステート](#savestate)|ユーザー ツールに関する情報を Windows レジストリに格納します。|
|[CUser ツールマネージャー::セットデフエクスク](#setdefext)|[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**カスタマイズ**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用する既定の拡張子を指定します。|
|[コントロール::セットフィルタ](#setfilter)|[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**カスタマイズ**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用するファイル フィルタを指定します。|

## <a name="remarks"></a>解説

ユーザー ツールをアプリケーションに組み込むには、次の操作を行う必要があります。

1. ユーザー ツール メニュー エントリのメニュー項目と関連するコマンド ID を予約します。

2. ユーザーがアプリケーションで定義できるユーザー・ツールごとに、順次コマンド ID を予約します。

3. [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)メソッドを呼び出し、メニュー コマンド ID、最初のユーザー ツール コマンド ID、および最後のユーザー ツール コマンド ID のパラメーターを指定します。

アプリケーションごとにグローバル`CUserToolsManager`オブジェクトは 1 つだけ存在します。

ユーザー ツールの例については、サンプル プロジェクトを参照してください。

## <a name="example"></a>例

オブジェクトへの参照を取得する方法と、新しいユーザー`CUserToolsManager`ツールを作成する方法を次の例に示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxuser ツールマネージャー.h

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a>CUser ツールマネージャー::新しいツールの作成

新しいユーザー ツールを作成します。

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>戻り値

新しく作成されたユーザー ツールへのポインター。 返される型は`CWinAppEx::EnableUserTools`*、pToolRTC*パラメーターとして渡される型と同じです。

### <a name="remarks"></a>解説

このメソッドは[、CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)の呼び出しで指定された範囲内の最初の使用可能なメニュー コマンド ID を検索し、ユーザー ツールにこの ID を割り当てます。

ツールの数が最大値に達した場合、このメソッドは失敗します。 このエラーは、範囲内のすべてのコマンド ID がユーザー ツールに割り当てられている場合に発生します。 ツールの最大数を取得するには[、CUserToolsManager::GetMaxTools](#getmaxtools)を呼び出します。 ツール リストにアクセスするには、[メソッド](#getusertools)を呼び出します。

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a>CUser ツールマネージャー::CUser ツールマネージャー

`CUserToolsManager` を構築します。 各アプリケーションには、ユーザー ツール マネージャーが 1 つ以上必要です。

```
CUserToolsManager();

CUserToolsManager(
    const UINT uiCmdToolsDummy,
    const UINT uiCmdFirst,
    const UINT uiCmdLast,
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),
    UINT uArgMenuID=0,
    UINT uInitDirMenuID=0);
```

### <a name="parameters"></a>パラメーター

*uiCmdツールダミー*<br/>
[in]フレームワークがユーザー ツール メニューのコマンド ID のプレースホルダーとして使用する符号なし整数。

*最初にコマンドを実行します。*<br/>
[in]最初のユーザー ツール コマンドのコマンド ID。

*をクリックします。*<br/>
[in]最後のユーザー ツール コマンドのコマンド ID。

*をクリックします。*<br/>
[in][CUser ツール マネージャー::CreateNewTool](#createnewtool)が作成するクラス。 このクラスを使用すると、既定の実装の代わりに[CUserTool クラス](../../mfc/reference/cusertool-class.md)の派生型を使用できます。

*をクリックします。*<br/>
[in]引数ポップアップ メニューのメニュー リソース ID。

*ユーイニトディルメニューID*<br/>
[in]初期ディレクトリポップアップ メニューのメニュー リソース ID。

### <a name="remarks"></a>解説

このコンストラクターを呼び出しません。 代わりに、ユーザー ツールを有効にするために[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出し[、CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager)を呼び出してへのポインターを取得します`CUserToolsManager`。 詳細については、「[ユーザー定義ツール](../../mfc/user-defined-tools.md)」を参照してください。

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a>ツールマネージャー::ツールを検索

指定したコマンド ID に関連付けられている[CUserTool クラス](../../mfc/reference/cusertool-class.md)オブジェクトへのポインターを返します。

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
[in]メニュー コマンドの識別子。

### <a name="return-value"></a>戻り値

成功した場合は[CUserTool](../../mfc/reference/cusertool-class.md) `CUserTool`クラスまたは派生オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

正常`FindTool`に実行された場合、返される型は[、CWinAppEx:::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)に対する*pToolRTC*パラメーターの型と同じです。

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a>ツールマネージャー::引数メニューID

[**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[引数]** メニューに関連付けられているリソース ID を返します。

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>戻り値

メニュー リソースの識別子。

### <a name="remarks"></a>解説

の*パラメーター*は[、](../../mfc/reference/cwinappex-class.md#enableusertools)リソースの ID を指定します。

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a>CUser ツールマネージャー::ゲットデフエクスク

[**ファイルを開く**] ダイアログ ボックス[(CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) が [**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用する既定の拡張子を返します。

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>戻り値

拡張機能を`CString`含むオブジェクトへの参照。

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a>コントロール::ゲットフィルター

[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用するファイル フィルタを返します。

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>戻り値

フィルターを`CString`含むオブジェクトへの参照。

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a>をクリックします。

[**ユーザー設定**] ダイアログ ボックスの [**ツール**] タブの **[初期ディレクトリ**] メニューに関連付けられているリソース ID を返します。

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>戻り値

メニュー リソース識別子。

### <a name="remarks"></a>解説

返される ID は[、CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)の*パラメーター*で指定されます。

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a>CUser ツールマネージャー::ゲットマックスツール

アプリケーションに割り当てることができるユーザー ツールの最大数を返します。

```
int GetMaxTools() const;
```

### <a name="return-value"></a>戻り値

割り当て可能なユーザー ツールの最大数。

### <a name="remarks"></a>解説

アプリケーションで割り当てることができるツールの最大数を取得します。 この数値は *、uiCmdFirst*から[、CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)に渡す*uiCmdLast*パラメーターまでの範囲内の ID の数です。

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a>ツールマネージャー::ツールエントリCmd

ユーザー ツールのメニュー項目プレースホルダーのコマンド ID を返します。

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>戻り値

プレースホルダーのコマンド ID。

### <a name="remarks"></a>解説

ユーザー ツールを有効にするには[、CWinAppEx::ユーザーツールを呼](../../mfc/reference/cwinappex-class.md#enableusertools)び出します。 *uiCmd ツールダミー*パラメーターは、ツール入力コマンドのコマンド ID を指定します。 このメソッドは、ツールエントリコマンド ID を返します。 メニュー内で使用されている ID は、メニューが表示されたときにユーザー ツールの一覧に置き換えられます。

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a>ツールマネージャー::ユーザーツール

ユーザー ツールの一覧への参照を返します。

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>戻り値

ユーザー ツールの一覧を含む[CObList クラス](../../mfc/reference/coblist-class.md)オブジェクトへの const 参照。

### <a name="remarks"></a>解説

[オブジェクト](../../mfc/reference/cusertoolsmanager-class.md)が保持しているユーザー ツールの一覧を取得します。 各ユーザー ツールは[、CUserTool クラス](../../mfc/reference/cusertool-class.md)型のオブジェクト、または から派生`CUserTool`した型のオブジェクトで表されます。 この型は、ユーザー ツールを有効にするために[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出すときに*pToolRTC*パラメーターによって指定されます。

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a>ツールマネージャー::ツールを呼び出します

指定したコマンド ID を持つユーザー ツールに関連付けられているアプリケーションを実行します。

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
[in]ユーザー ツールに関連付けられているメニュー コマンド ID。

### <a name="return-value"></a>戻り値

ユーザー ツールに関連付けられたコマンドが正常に実行された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*uiCmdId*で指定されたコマンド ID を持つユーザー ツールに関連付けられたアプリケーションを実行します。

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a>ツールマネージャー::IsUserツールCmd

コマンド ID がユーザー ツールに関連付けられているかどうかを判断します。

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
[in]メニュー項目のコマンド ID。

### <a name="return-value"></a>戻り値

指定されたコマンド ID がユーザー ツールに関連付けられている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、指定されたコマンド ID がコマンド ID の範囲内にあるかどうかをチェックします。 ユーザー ツールを有効にするために[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出すときに範囲を指定します。

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a>CUser ツールマネージャー::ロードステート

Windows レジストリからユーザー ツールに関する情報を読み込みます。

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]Windows レジストリ キーのパス。

### <a name="return-value"></a>戻り値

状態が正常に読み込まれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、Windows レジストリ`CUserToolsManager`からオブジェクトの状態を読み込みます。

通常、このメソッドを直接呼び出すわけではありません。 [CWinAppEx::ロードステート](../../mfc/reference/cwinappex-class.md#loadstate)は、ワークスペース初期化プロセスの一部として呼び出します。

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a>CUserツールマネージャー::ツールダウンの移動

指定したユーザー ツールをユーザー ツールの一覧の下に移動します。

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pツール*<br/>
[in]移動するユーザー ツールを指定します。

### <a name="return-value"></a>戻り値

ユーザー ツールが正常に下に移動された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*pTool*が指定したツールが内部リストにない場合、またはツールがリストの最後にある場合、このメソッドは失敗します。

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a>CUserツールマネージャー::ムーブツールアップ

指定したユーザー ツールをユーザー ツールの一覧の上に移動します。

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pツール*<br/>
[in]移動するユーザー ツールを指定します。

### <a name="return-value"></a>戻り値

ユーザー ツールが正常に上に移動した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

*pTool*パラメーターで指定されたツールが内部リストにない場合、またはツールがリストの最初のツール項目である場合、このメソッドは失敗します。

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a>ツールマネージャー::ツールの削除

指定したユーザー ツールをアプリケーションから削除します。

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pツール*<br/>
[イン、アウト]削除するユーザー ツールへのポインター。

### <a name="return-value"></a>戻り値

ツールが正常に削除された場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ツールが正常に削除されると、このメソッドは*pTool*を削除します。

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a>CUser ツールマネージャー::セーブステート

ユーザー ツールに関する情報を Windows レジストリに格納します。

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]Windows レジストリ キーへのパス。

### <a name="return-value"></a>戻り値

状態が正常に保存された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、オブジェクトの現在の`CUserToolsManager`状態を Windows レジストリに格納します。

通常、このメソッドを直接呼び出す必要はありません、 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)は、アプリケーションのワークスペースのシリアル化プロセスの一部として自動的に呼び出します。

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a>CUser ツールマネージャー::セットデフエクスク

[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**カスタマイズ**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用する既定の拡張子を指定します。

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>パラメーター

*ストデフエクスク*<br/>
[in]既定のファイル名拡張子を含むテキスト文字列。

### <a name="remarks"></a>解説

ユーザーがユーザー ツールに関連付けるアプリケーションを選択したときに表示される [**ファイルを開く**] ダイアログ ボックスで、既定のファイル名拡張子を指定します。 デフォルトは "exe" です。

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a>コントロール::セットフィルタ

[**ファイルを開く**] ダイアログ ボックス[(CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) が [**カスタマイズ**] ダイアログ ボックスの [**ツール**] タブの **[コマンド**] フィールドで使用するファイル フィルタを指定します。

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>パラメーター

*スズフィルター*<br/>
[in]フィルタを指定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool クラス](../../mfc/reference/cusertool-class.md)
