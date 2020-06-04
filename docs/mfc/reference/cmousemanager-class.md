---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 1394a1b47a86022e37b11e032b87ee2a2a369862
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752810"
---
# <a name="cmousemanager-class"></a>クラス

ユーザーがビュー内をダブルクリックしたときに、特定の[CView](../../mfc/reference/cview-class.md)オブジェクトに異なるコマンドを関連付けることができます。

## <a name="syntax"></a>構文

```
class CMouseManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[マウスマネージャー::ビューの追加](#addview)|[`CView`**カスタマイズ]** ダイアログ ボックスにオブジェクトを追加します。 [**カスタマイズ]** ダイアログ ボックスでは、表示されている各ビューのコマンドにダブルクリックを関連付けることができます。|
|[マウスマネージャー::コマンドを表示します。](#getviewdblclickcommand)|指定されたビュー内でユーザーがダブルクリックしたときに実行されるコマンドを返します。|
|[マウスマネージャー::ビューアイコンId](#getviewiconid)|指定されたビュー ID に関連付けられたアイコンを返します。|
|[マウスマネージャー::取得ビューIdバイネーム](#getviewidbyname)|指定されたビュー名に関連付けられたビュー ID を返します。|
|[マウスマネージャー::取得ビュー名](#getviewnames)|追加されたすべてのビュー名のリストを取得します。|
|[マウスマネージャー::ロードステート](#loadstate)|Windows`CMouseManager`レジストリから状態を読み込みます。|
|[マウスマネージャー::セーブステート](#savestate)|状態を`CMouseManager`Windows レジストリに書き込みます。|
|[マウスマネージャー::コマンドフォードブルク](#setcommandfordblclk)|指定されたコマンドと指定されたビューを関連付けます。|

## <a name="remarks"></a>解説

クラス`CMouseManager`はオブジェクトのコレクションを`CView`保持します。 各ビューは、名前と ID で識別されます。 これらのビューは、[**カスタマイズ]** ダイアログ ボックスに表示されます。 ユーザーは、[**カスタマイズ]** ダイアログ ボックスを使用して、任意のビューに関連付けられているコマンドを変更できます。 関連付けられたコマンドは、ユーザーがそのビュー内でダブルクリックしたときに実行されます。 コーディングの観点からこれをサポートするには、WM_LBUTTONDBLCLK メッセージを処理し、その`CView`オブジェクトのコードで[CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick)関数を呼び出す必要があります。

オブジェクトは手動で`CMouseManager`作成しないでください。 アプリケーションのフレームワークによって作成されます。 また、ユーザーがアプリケーションを終了すると、自動的に破棄されます。 アプリケーションのマウス マネージャーへのポインターを取得するには[、CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxmousemanager.h

## <a name="cmousemanageraddview"></a><a name="addview"></a>マウスマネージャー::ビューの追加

カスタム マウス動作をサポートする[CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)に[CView](../../mfc/reference/cview-class.md)オブジェクトを登録します。

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ビュー ID。

*を返します。*<br/>
[in]ビュー名を参照するリソース文字列 ID。

*uiアイコンId*<br/>
[in]ビュー アイコン ID。

*Iid*<br/>
[in]ビュー ID。

*名前を表示します。*<br/>
[in]ビュー名。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

カスタム マウス動作をサポートするには、ビューをオブジェクトに登録する`CMouseManager`必要があります。 クラスから派生したオブジェクト`CView`は、マウス マネージャーで登録できます。 ビューに関連付けられた文字列とアイコンは、[**カスタマイズ**] ダイアログ ボックスの **[マウス**] タブに表示されます。

*iViewId*や*iId*などのビュー ID を作成および管理するのはプログラマの責任です。

カスタム のマウス動作を提供する方法の詳細については、「[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)」を参照してください。

### <a name="example"></a>例

メソッドとクラスの`CMouseManager`メソッドを使用してオブジェクトへのポインターを取得する方法を`CWinAppEx::GetMouseManager`次の`AddView`例に示します。 `CMouseManager` このコード スニペットは[、状態コレクションのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a>マウスマネージャー::コマンドを表示します。

指定されたビュー内でユーザーがダブルクリックしたときに実行されるコマンドを返します。

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
[in]ビュー ID。

### <a name="return-value"></a>戻り値

ビューがコマンドに関連付けられている場合はコマンド ID。それ以外の場合は 0。

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a>マウスマネージャー::ビューアイコンId

ビュー ID に関連付けられているアイコンを取得します。

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ビュー ID。

### <a name="return-value"></a>戻り値

成功した場合はアイコン リソース識別子。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ビューが[CMouseManager::AddView](#addview)を使用して最初に登録されていない場合は失敗します。

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a>マウスマネージャー::取得ビューIdバイネーム

ビュー名に関連付けられているビュー ID を取得します。

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]ビュー名。

### <a name="return-value"></a>戻り値

成功した場合はビュー ID。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは[、CMouseManager::AddView](#addview)を使用して登録されたビューを検索します。

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a>マウスマネージャー::取得ビュー名

登録されているすべてのビュー名のリストを取得します。

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>パラメーター

*名前の一覧*<br/>
[アウト]オブジェクトへの`CStringList`参照。

### <a name="remarks"></a>解説

このメソッドは`listOfNames`[、CMouseManager::AddView](#addview)を使用して登録されたすべてのビューの名前をパラメーターに入力します。

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a>マウスマネージャー::ロードステート

[CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)の状態をレジストリから読み込みます。

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]レジストリ キーのパス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

レジストリから読み込まれた状態情報には、登録済みのビュー、ビュー識別子、および関連するコマンドが含まれます。 パラメーター *lpszProfileName*が NULL の場合、`CMouseManager`この関数は[、CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)によって制御される既定のレジストリの場所からデータを読み込みます。

ほとんどの場合、この関数を直接呼び出す必要はありません。 これは、ワークスペースの初期化プロセスの一部として呼び出されます。 ワークスペース初期化プロセスの詳細については[、「CWinAppEx::LoadState」](../../mfc/reference/cwinappex-class.md#loadstate)を参照してください。

## <a name="cmousemanagersavestate"></a><a name="savestate"></a>マウスマネージャー::セーブステート

[CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)の状態をレジストリに書き込みます。

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]レジストリ キーのパス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

レジストリに書き込まれる状態情報には、登録されているすべてのビュー、ビュー識別子、および関連するコマンドが含まれます。 パラメーター *lpszProfileName*が NULL の場合、`CMouseManager`この関数は[、CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)によって制御される既定のレジストリの場所にデータを書き込みます。

ほとんどの場合、この関数を直接呼び出す必要はありません。 これは、ワークスペースのシリアル化プロセスの一部として呼び出されます。 ワークスペースのシリアル化プロセスの詳細については[、「CWinAppEx::SaveState」を参照してください](../../mfc/reference/cwinappex-class.md#savestate)。

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a>マウスマネージャー::コマンドフォードブルク

カスタム コマンドを、マウス マネージャーに最初に登録されたビューに関連付けます。

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ビュー識別子。

*Uicmd*<br/>
[in]コマンド識別子。

### <a name="remarks"></a>解説

ビューにカスタム コマンドを関連付けるには、まず[CMouseManager::AddView](#addview)を使用してビューを登録する必要があります。 この`AddView`メソッドには、入力パラメーターとしてビュー識別子が必要です。 ビューを登録すると、 に指定したのと`CMouseManager::SetCommandForDblClk`同じビュー識別子入力パラメータを使用して`AddView`呼び出すことができます。 その後、登録されているビューでユーザーがマウスをダブルクリックすると、アプリケーションは uiCmd で示されたコマンドを実行*します。* カスタム のマウス動作をサポートするには、マウス マネージャーに登録されているビューをカスタマイズする必要があります。 カスタム マウスの動作の詳細については、「[キーボードとマウスのカスタマイズ](../keyboard-and-mouse-customization.md)」を参照してください。

*uiCmd*が 0 に設定されている場合、指定されたビューはコマンドに関連付けなくなります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)
