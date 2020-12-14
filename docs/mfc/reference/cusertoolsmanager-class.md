---
description: '詳細情報: Cuserツールマネージャークラス'
title: Cuserツールマネージャークラス
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
ms.openlocfilehash: 1c6b3b6ec2912a0093929ac117d878d54ed9757f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344953"
---
# <a name="cusertoolsmanager-class"></a>Cuserツールマネージャークラス

アプリケーション内の [Cusertool クラス](../../mfc/reference/cusertool-class.md) オブジェクトのコレクションを保持します。 ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 `CUserToolsManager` オブジェクトは、ユーザーまたは開発者がアプリケーションに新しいユーザー ツールを追加できるようにします。 ユーザー ツールに関連するコマンドの実行をサポートし、Windows レジストリにユーザー ツールに関する情報を保存します。

## <a name="syntax"></a>構文

```
class CUserToolsManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cuserツールマネージャー:: Cuserツールマネージャー](#cusertoolsmanager)|`CUserToolsManager` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cuserツールマネージャー:: CreateNewTool](#createnewtool)|新しいユーザーツールを作成します。|
|[Cusertools Manager:: FindTool](#findtool)|指定した `CMFCUserTool` コマンド ID に関連付けられているオブジェクトへのポインターを返します。|
|[Cuserツールマネージャー:: GetArgumentsMenuID](#getargumentsmenuid)|[**カスタマイズ**] ダイアログボックスの [**ツール**] タブにある [**引数**] メニューに関連付けられているリソース ID を返します。|
|[Cuserツールマネージャー:: GetDefExt](#getdefext)|[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで [**ファイルを開く**] ダイアログボックス ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) で使用する既定の拡張機能を返します。|
|[Cuserツールマネージャー:: GetFilter](#getfilter)|[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用するファイルフィルターを返します。|
|[Cuserツールマネージャー:: GetInitialDirMenuID](#getinitialdirmenuid)|[**カスタマイズ**] ダイアログボックスの [**ツール**] タブの [**初期ディレクトリ**] メニューに関連付けられているリソース ID を返します。|
|[Cusertools Manager:: GetMaxTools](#getmaxtools)|アプリケーションで割り当てることができるユーザーツールの最大数を返します。|
|[CUserToolsManager:: GetToolsEntryCmd](#gettoolsentrycmd)|ユーザーツールのメニュー項目プレースホルダーのコマンド ID を返します。|
|[Cusertools Manager:: GetUserTools](#getusertools)|ユーザーツールのリストへの参照を返します。|
|[Cusertools Manager:: InvokeTool](#invoketool)|指定されたコマンド ID を持つユーザーツールに関連付けられているアプリケーションを実行します。|
|[CUserToolsManager:: IsUserToolCmd](#isusertoolcmd)|コマンド ID がユーザーツールに関連付けられているかどうかを判断します。|
|[Cuserツールマネージャー:: LoadState](#loadstate)|Windows レジストリからユーザーツールに関する情報を読み込みます。|
|[CUserToolsManager:: MoveToolDown](#movetooldown)|ユーザーツールの一覧内で、指定されたユーザーツールを下へ移動します。|
|[CUserToolsManager:: MoveToolUp](#movetoolup)|指定されたユーザーツールをユーザーツールの一覧内で上に移動します。|
|[Cusertools Manager:: RemoveTool](#removetool)|指定されたユーザーツールをアプリケーションから削除します。|
|[Cuserツールマネージャー:: SaveState](#savestate)|Windows レジストリにユーザーツールに関する情報を格納します。|
|[Cuserツールマネージャー:: SetDefExt](#setdefext)|[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用する既定の拡張機能を指定します。|
|[Cuserツールマネージャー:: SetFilter](#setfilter)|[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用するファイルフィルターを指定します。|

## <a name="remarks"></a>解説

アプリケーションにユーザーツールを組み込むには、次のことを行う必要があります。

1. メニュー項目と、ユーザーツールメニューエントリに関連付けられたコマンド ID を予約します。

2. ユーザーがアプリケーションで定義できる各ユーザーツールの順次コマンド ID を予約します。

3. [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)メソッドを呼び出し、次のパラメーターを指定します。メニューコマンド id、最初のユーザーツールコマンド id、最後のユーザーツールコマンド id。

アプリケーションごとに1つのグローバルオブジェクトしか存在できませ `CUserToolsManager` ん。

ユーザーツールの例については、VisualStudioDemo サンプルプロジェクトを参照してください。

## <a name="example"></a>例

次の例は、オブジェクトへの参照を取得する方法と、新しいユーザーツールを作成する方法を示して `CUserToolsManager` います。 このコードスニペットは、 [Visual Studio のデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CUserToolsManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxusertoolsmanager

## <a name="cusertoolsmanagercreatenewtool"></a><a name="createnewtool"></a> Cuserツールマネージャー:: CreateNewTool

新しいユーザーツールを作成します。

```
CUserTool* CreateNewTool();
```

### <a name="return-value"></a>戻り値

新しく作成されたユーザーツールへのポインター。または、ユーザーツールの数が最大値を超えた場合は NULL。 返される型は、 `CWinAppEx::EnableUserTools` *Ptoolrtc* パラメーターとしてに渡される型と同じです。

### <a name="remarks"></a>解説

このメソッドは、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) の呼び出しで指定された範囲内で使用可能な最初のメニューコマンド id を検索し、ユーザーツールにこの id を割り当てます。

ツールの数が最大値に達した場合、メソッドは失敗します。 このエラーは、範囲内のすべてのコマンド Id がユーザーツールに割り当てられている場合に発生します。 [Cusertools manager:: GetMaxTools](#getmaxtools)を呼び出すことによって、ツールの最大数を取得できます。 [Cusertools manager:: getusertools](#getusertools)メソッドを呼び出すと、ツールの一覧にアクセスできます。

## <a name="cusertoolsmanagercusertoolsmanager"></a><a name="cusertoolsmanager"></a> Cuserツールマネージャー:: Cuserツールマネージャー

`CUserToolsManager` を構築します。 各アプリケーションには、ユーザーツールマネージャーが1つだけ必要です。

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

*uiCmdToolsDummy*<br/>
からフレームワークがユーザーツールメニューのコマンド ID のプレースホルダーとして使用する符号なし整数。

*uiCmdFirst*<br/>
から最初のユーザーツールコマンドのコマンド ID。

*uiCmdLast*<br/>
から最後のユーザーツールコマンドのコマンド ID。

*pToolRTC*<br/>
から [Cuserツールマネージャー:: CreateNewTool](#createnewtool) が作成するクラス。 このクラスを使用すると、既定の実装ではなく、 [Cusertool クラス](../../mfc/reference/cusertool-class.md) の派生型を使用できます。

*uArgMenuID*<br/>
から引数ポップアップメニューのメニューリソース ID。

*uInitDirMenuID*<br/>
から初期ディレクトリポップアップメニューのメニューリソース ID。

### <a name="remarks"></a>解説

このコンストラクターを呼び出さないでください。 代わりに、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) を呼び出してユーザーツールを有効にし、 [CWinAppEx:: getusertools manager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager) を呼び出してへのポインターを取得し `CUserToolsManager` ます。 詳細については、「 [ユーザー定義ツール](../../mfc/user-defined-tools.md)」を参照してください。

## <a name="cusertoolsmanagerfindtool"></a><a name="findtool"></a> Cusertools Manager:: FindTool

指定したコマンド ID に関連付けられている [Cusertool クラス](../../mfc/reference/cusertool-class.md) オブジェクトへのポインターを返します。

```
CUserTool* FindTool(UINT uiCmdId) const;
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
からメニューコマンドの識別子。

### <a name="return-value"></a>戻り値

成功した場合は [Cusertool クラス](../../mfc/reference/cusertool-class.md) または派生オブジェクトへのポインター `CUserTool` 。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`FindTool`が成功した場合、返される型は、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)に対する *ptoolrtc* パラメーターの型と同じになります。

## <a name="cusertoolsmanagergetargumentsmenuid"></a><a name="getargumentsmenuid"></a> Cuserツールマネージャー:: GetArgumentsMenuID

[**カスタマイズ**] ダイアログボックスの [**ツール**] タブにある [**引数**] メニューに関連付けられているリソース ID を返します。

```
UINT GetArgumentsMenuID() const;
```

### <a name="return-value"></a>戻り値

メニューリソースの識別子。

### <a name="remarks"></a>解説

[CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)の *Uargmenuid* パラメーターは、リソースの ID を指定します。

## <a name="cusertoolsmanagergetdefext"></a><a name="getdefext"></a> Cuserツールマネージャー:: GetDefExt

[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで [**ファイルを開く**] ダイアログボックス ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) で使用する既定の拡張機能を返します。

```
const CString& GetDefExt() const;
```

### <a name="return-value"></a>戻り値

拡張を含むオブジェクトへの参照 `CString` 。

## <a name="cusertoolsmanagergetfilter"></a><a name="getfilter"></a> Cuserツールマネージャー:: GetFilter

[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用するファイルフィルターを返します。

```
const CString& GetFilter() const;
```

### <a name="return-value"></a>戻り値

フィルターを格納し `CString` ているオブジェクトへの参照。

## <a name="cusertoolsmanagergetinitialdirmenuid"></a><a name="getinitialdirmenuid"></a> Cuserツールマネージャー:: GetInitialDirMenuID

[**カスタマイズ**] ダイアログボックスの [**ツール**] タブの [**初期ディレクトリ**] メニューに関連付けられているリソース ID を返します。

```
UINT GetInitialDirMenuID() const;
```

### <a name="return-value"></a>戻り値

メニューリソース識別子。

### <a name="remarks"></a>解説

返された ID は、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)の *Uinitdirmenuid* パラメーターで指定されます。

## <a name="cusertoolsmanagergetmaxtools"></a><a name="getmaxtools"></a> Cusertools Manager:: GetMaxTools

アプリケーションで割り当てることができるユーザーツールの最大数を返します。

```
int GetMaxTools() const;
```

### <a name="return-value"></a>戻り値

割り当てることができるユーザーツールの最大数。

### <a name="remarks"></a>解説

アプリケーションで割り当てることができるツールの最大数を取得するには、このメソッドを呼び出します。 この数値は、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)に渡す *uiCmdLast* パラメーターを通じて、 *UiCmdFirst* からの範囲の id の数です。

## <a name="cusertoolsmanagergettoolsentrycmd"></a><a name="gettoolsentrycmd"></a> CUserToolsManager:: GetToolsEntryCmd

ユーザーツールのメニュー項目プレースホルダーのコマンド ID を返します。

```
UINT GetToolsEntryCmd() const;
```

### <a name="return-value"></a>戻り値

プレースホルダーのコマンド ID。

### <a name="remarks"></a>解説

ユーザーツールを有効にするには、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出します。 *UiCmdToolsDummy* パラメーターは、ツールエントリコマンドのコマンド ID を指定します。 このメソッドは、ツールエントリコマンド ID を返します。 その ID がメニューで使用されている場合は、メニューが表示されたときにユーザーツールの一覧に置き換えられます。

## <a name="cusertoolsmanagergetusertools"></a><a name="getusertools"></a> Cusertools Manager:: GetUserTools

ユーザーツールのリストへの参照を返します。

```
const CObList& GetUserTools() const;
```

### <a name="return-value"></a>戻り値

ユーザーツールの一覧を含む、 [CObList クラス](../../mfc/reference/coblist-class.md) オブジェクトへの const 参照。

### <a name="remarks"></a>解説

[Cusertools manager](../../mfc/reference/cusertoolsmanager-class.md)オブジェクトが保持するユーザーツールの一覧を取得するには、このメソッドを呼び出します。 各ユーザーツールは、 [Cusertool クラス](../../mfc/reference/cusertool-class.md) 型のオブジェクト、またはから派生した型で表され `CUserTool` ます。 この型は、 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出してユーザーツールを有効にするときに、 *ptoolrtc* パラメーターによって指定されます。

## <a name="cusertoolsmanagerinvoketool"></a><a name="invoketool"></a> Cusertools Manager:: InvokeTool

指定されたコマンド ID を持つユーザーツールに関連付けられているアプリケーションを実行します。

```
BOOL InvokeTool(UINT uiCmdId);
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
からユーザーツールに関連付けられているメニューコマンド ID。

### <a name="return-value"></a>戻り値

ユーザーツールに関連付けられたコマンドが正常に実行された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*UiCmdId* によって指定されたコマンド ID を持つユーザーツールに関連付けられているアプリケーションを実行するには、このメソッドを呼び出します。

## <a name="cusertoolsmanagerisusertoolcmd"></a><a name="isusertoolcmd"></a> CUserToolsManager:: IsUserToolCmd

コマンド ID がユーザーツールに関連付けられているかどうかを判断します。

```
BOOL IsUserToolCmd(UINT uiCmdId) const;
```

### <a name="parameters"></a>パラメーター

*uiCmdId*<br/>
からメニュー項目のコマンド ID。

### <a name="return-value"></a>戻り値

特定のコマンド ID がユーザーツールに関連付けられている場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメソッドは、指定されたコマンド ID がコマンド ID の範囲内にあるかどうかを確認します。 [CWinAppEx:: EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)を呼び出してユーザーツールを有効にする場合は、範囲を指定します。

## <a name="cusertoolsmanagerloadstate"></a><a name="loadstate"></a> Cuserツールマネージャー:: LoadState

Windows レジストリからユーザーツールに関する情報を読み込みます。

```
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からWindows レジストリキーのパス。

### <a name="return-value"></a>戻り値

状態が正常に読み込まれた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメソッドは、 `CUserToolsManager` Windows レジストリからオブジェクトの状態を読み込みます。

通常、このメソッドを直接呼び出さないでください。 [CWinAppEx:: LoadState は](../../mfc/reference/cwinappex-class.md#loadstate) 、ワークスペースの初期化プロセスの一部としてそれを呼び出します。

## <a name="cusertoolsmanagermovetooldown"></a><a name="movetooldown"></a> CUserToolsManager:: MoveToolDown

ユーザーツールの一覧内で、指定されたユーザーツールを下へ移動します。

```
BOOL MoveToolDown(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pTool*<br/>
から移動するユーザーツールを指定します。

### <a name="return-value"></a>戻り値

ユーザーツールが正常に移動された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Ptool* によって指定されたツールが内部リストにない場合、またはツールが一覧の最後にある場合、メソッドは失敗します。

## <a name="cusertoolsmanagermovetoolup"></a><a name="movetoolup"></a> CUserToolsManager:: MoveToolUp

指定されたユーザーツールをユーザーツールの一覧内で上に移動します。

```
BOOL MoveToolUp(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pTool*<br/>
から移動するユーザーツールを指定します。

### <a name="return-value"></a>戻り値

ユーザーツールが正常に移動した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

*Ptool* パラメーターが指定したツールが内部リストにない場合、またはツールがリスト内の最初のツール項目である場合、メソッドは失敗します。

## <a name="cusertoolsmanagerremovetool"></a><a name="removetool"></a> Cusertools Manager:: RemoveTool

指定されたユーザーツールをアプリケーションから削除します。

```
BOOL RemoveTool(CUserTool* pTool);
```

### <a name="parameters"></a>パラメーター

*pTool*<br/>
[入力、出力]削除するユーザーツールへのポインター。

### <a name="return-value"></a>戻り値

ツールが正常に削除された場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ツールが正常に削除された場合、このメソッドは *Ptool* を削除します。

## <a name="cusertoolsmanagersavestate"></a><a name="savestate"></a> Cuserツールマネージャー:: SaveState

Windows レジストリにユーザーツールに関する情報を格納します。

```
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からWindows レジストリキーのパス。

### <a name="return-value"></a>戻り値

状態が正常に保存された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

メソッドは、オブジェクトの現在の状態を `CUserToolsManager` Windows レジストリに格納します。

通常、このメソッドを直接呼び出す必要はありません。 [CWinAppEx:: SaveState](../../mfc/reference/cwinappex-class.md#savestate) は、アプリケーションのワークスペースのシリアル化プロセスの一部として自動的に呼び出します。

## <a name="cusertoolsmanagersetdefext"></a><a name="setdefext"></a> Cuserツールマネージャー:: SetDefExt

[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用する既定の拡張機能を指定します。

```cpp
void SetDefExt(const CString& strDefExt);
```

### <a name="parameters"></a>パラメーター

*strDefExt*<br/>
から既定のファイル名拡張子を含むテキスト文字列。

### <a name="remarks"></a>解説

[ **ファイルを開く** ] ダイアログボックスで既定のファイル名拡張子を指定するには、このメソッドを呼び出します。これは、ユーザーがユーザーツールに関連付けるアプリケーションを選択したときに表示されます。 既定値は "exe" です。

## <a name="cusertoolsmanagersetfilter"></a><a name="setfilter"></a> Cuserツールマネージャー:: SetFilter

[**ファイルを開く**] ダイアログボックス ( [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)) で、[**ユーザー設定**] ダイアログボックスの [**ツール**] タブの [**コマンド**] フィールドで使用するファイルフィルターを指定します。

```cpp
void SetFilter(const CString& strFilter);
```

### <a name="parameters"></a>パラメーター

*strFilter*<br/>
からフィルターを指定します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[CUserTool クラス](../../mfc/reference/cusertool-class.md)
