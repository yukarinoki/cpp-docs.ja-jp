---
title: CDockState クラス
ms.date: 11/04/2016
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
ms.openlocfilehash: 9850486407ee7550ee866a10e656d45ad18fc196
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753261"
---
# <a name="cdockstate-class"></a>CDockState クラス

いくつかのドッキング コントロール バーの状態を 2 次メモリ (ファイル) で読み込み、アンロード、またはクリアするシリアル化された `CObject` クラスです。

## <a name="syntax"></a>構文

```
class CDockState : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDockState::クリア](#clear)|ドックの状態情報をクリアします。|
|[クドックステート::ゲットバージョン](#getversion)|格納されているバーの状態のバージョン番号を取得します。|
|[Cドックステート::ロードステート](#loadstate)|レジストリまたはから状態情報を取得します。INI ファイル。|
|[Cドックステート::セーブステート](#savestate)|状態情報をレジストリまたは INI ファイルに保存します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クドックステート::m_arrBarInfo](#m_arrbarinfo)|各コントロール バーに 1 つのエントリを持つ、格納されているドッキング状態情報へのポインターの配列。|

## <a name="remarks"></a>解説

ドッキング状態には、バーのサイズと位置、およびドッキングされているかどうかが含まれます。 格納されているドッキング状態を取得する際`CDockState`に、バーの位置をチェックし、バーが現在の画面設定で表示されない場合は`CDockState`、バーの位置を拡大縮小して表示します。 主な目的`CDockState`は、多数のコントロール バーの状態全体を保持し、その状態を保存してレジストリ 、アプリケーションの .INI ファイル、または`CArchive`オブジェクトの内容の一部としてバイナリ形式で指定します。

このバーには、ツールバー、ステータス バー、ダイアログ バーなど、任意のドッキング可能なコントロール バーを使用できます。 `CDockState`オブジェクトは、オブジェクトを介してファイルに書き込`CArchive`まれ、ファイルから読み込まれます。

[CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate)は、すべてのフレーム ウィンドウの`CControlBar`オブジェクトの状態情報を取得し、オブジェクトに`CDockState`配置します。 その後、オブジェクトの`CDockState`内容を[シリアル化](../../mfc/reference/cobject-class.md#serialize)または[CDockState::SaveState](#savestate)を使用してストレージに書き込むことができます。 後でフレーム ウィンドウのコントロール バーの状態を復元する場合は、状態を`Serialize`[CDockState::LoadState](#loadstate)で読み込み[、CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate)を使用して、保存された状態をフレーム ウィンドウのコントロール バーに適用します。

コントロール バーのドッキングの詳細については、「[コントロール バー](../../mfc/control-bars.md)」、[ツールバー: ドッキングとフローティング](../../mfc/docking-and-floating-toolbars.md)、および[フレーム ウィンドウ](../../mfc/frame-windows.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxadv.h

## <a name="cdockstateclear"></a><a name="clear"></a>CDockState::クリア

`CDockState`オブジェクトに格納されているすべてのドッキング情報をクリアします。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

これには、バーがドッキングされているかどうかだけでなく、バーのサイズと位置、表示されているかどうかも含まれます。

## <a name="cdockstategetversion"></a><a name="getversion"></a>クドックステート::ゲットバージョン

格納されているバーの状態のバージョン番号を取得します。

```
DWORD GetVersion();
```

### <a name="return-value"></a>戻り値

格納されたバー情報が現在のバーの状態よりも古い場合は 1。格納されたバー情報が現在のバーの状態と同じである場合は 2。

### <a name="remarks"></a>解説

バージョンサポートを使用すると、変更されたバーは新しい永続プロパティを追加でき、以前のバージョンのバーで作成された永続状態を検出して読み込むことができます。

## <a name="cdockstateloadstate"></a><a name="loadstate"></a>Cドックステート::ロードステート

レジストリまたはから状態情報を取得します。INI ファイル。

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリのキーを指定する null テミスト文字列へのポイント。

### <a name="remarks"></a>解説

プロファイル名は、アプリケーションの セクションです。INI ファイルまたはバーの状態情報を含むレジストリ。 コントロール バーの状態情報は、レジストリまたは に保存できます。INI ファイル`SaveState`と .

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a>クドックステート::m_arrBarInfo

オブジェクト`CPtrArray`内に状態情報を保存した各コントロール バーの、格納されているコントロール バー情報へのポインターの配列です`CDockState`。

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a>Cドックステート::セーブステート

状態情報をレジストリまたはに保存します。INI ファイル。

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリのキーを指定する null テミスト文字列へのポイント。

### <a name="remarks"></a>解説

プロファイル名は、アプリケーションの セクションです。INI ファイルまたはコントロール バーの状態情報を含むレジストリ。 `SaveState`また、現在の画面サイズも保存します。 コントロール バーの情報は、レジストリまたは から取得できます。INI ファイル`LoadState`と .

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
