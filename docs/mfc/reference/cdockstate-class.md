---
description: '詳細情報: CDockState クラス'
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
ms.openlocfilehash: 4bdc17ec5a09b812609b8aa71e3f361603c1106f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184960"
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
|[CDockState:: Clear](#clear)|ドッキング状態情報をクリアします。|
|[CDockState:: GetVersion](#getversion)|格納されているバーの状態のバージョン番号を取得します。|
|[CDockState:: LoadState](#loadstate)|レジストリまたはから状態情報を取得します。INI ファイル。|
|[CDockState:: SaveState](#savestate)|レジストリまたは INI ファイルに状態情報を保存します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDockState:: m_arrBarInfo](#m_arrbarinfo)|コントロールバーごとに1つのエントリを持つ格納されたドッキング状態情報へのポインターの配列。|

## <a name="remarks"></a>解説

Dock の状態には、バーのサイズと位置、およびドッキングされているかどうかが含まれます。 格納されているドッキング状態を取得すると、は `CDockState` バーの位置を確認し、現在の画面設定でバーが表示されない場合は、 `CDockState` バーの位置を拡大して表示されるようにします。 の主な目的 `CDockState` は、多数のコントロールバーの状態全体を保持し、その状態を保存して、レジストリ (アプリケーションの) に読み込むことです。INI ファイル。または、オブジェクトの内容の一部としてバイナリ形式で作成さ `CArchive` れます。

バーには、ツールバー、ステータスバー、またはダイアログバーを含む、任意のドッキング可能なコントロールバーを使用できます。 `CDockState` オブジェクトは、オブジェクトを使用して、ファイルとの間で読み書きされ `CArchive` ます。

[CFrameWnd:: GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate) は、すべてのフレームウィンドウのオブジェクトの状態情報を取得 `CControlBar` し、オブジェクトに格納し `CDockState` ます。 その後、 `CDockState` [シリアル化](../../mfc/reference/cobject-class.md#serialize) または [CDockState:: SaveState](#savestate)を使用して、オブジェクトの内容をストレージに書き込むことができます。 後でフレームウィンドウ内のコントロールバーの状態を復元する場合 `Serialize` は、または [CDockState:: LoadState](#loadstate)を使用して状態を読み込み、次に [CFrameWnd:: SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate) を使用して、保存した状態をフレームウィンドウのコントロールバーに適用できます。

ドッキングコントロールバーの詳細については、「 [コントロール](../../mfc/control-bars.md)バー、 [ツールバー: ドッキングとフローティング](../../mfc/docking-and-floating-toolbars.md)、および [フレームウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CDockState`

## <a name="requirements"></a>要件

**ヘッダー:** afxadv

## <a name="cdockstateclear"></a><a name="clear"></a> CDockState:: Clear

オブジェクトに格納されているすべてのドッキング情報をクリアするには、この関数を呼び出し `CDockState` ます。

```cpp
void Clear();
```

### <a name="remarks"></a>解説

これには、バーがドッキングされているかどうかだけでなく、バーのサイズと位置、および表示されるかどうかも含まれます。

## <a name="cdockstategetversion"></a><a name="getversion"></a> CDockState:: GetVersion

格納されているバーの状態のバージョン番号を取得するには、この関数を呼び出します。

```
DWORD GetVersion();
```

### <a name="return-value"></a>戻り値

格納されているバー情報が現在のバーの状態よりも古い場合は1。格納されているバーの情報が現在のバーの状態と同じ場合は2。

### <a name="remarks"></a>解説

バージョンのサポートにより、変更されたバーで新しい永続的なプロパティを追加できるようになります。また、以前のバージョンのバーで作成された永続的な状態を検出して読み込むこともできます。

## <a name="cdockstateloadstate"></a><a name="loadstate"></a> CDockState:: LoadState

レジストリまたはから状態情報を取得するには、この関数を呼び出します。INI ファイル。

```cpp
void LoadState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリ内のキーを指定する、null ではない文字列を指します。

### <a name="remarks"></a>解説

プロファイル名は、アプリケーションののセクションです。INI ファイルまたはバーの状態情報を含むレジストリ。 コントロールバーの状態情報をレジストリまたはに保存できます。を使用した INI ファイル `SaveState` 。

## <a name="cdockstatem_arrbarinfo"></a><a name="m_arrbarinfo"></a> CDockState:: m_arrBarInfo

`CPtrArray`オブジェクトに状態情報が保存されている各コントロールバーの、格納されているコントロールバー情報へのポインターの配列であるオブジェクト `CDockState` 。

```
CPtrArray m_arrBarInfo;
```

## <a name="cdockstatesavestate"></a><a name="savestate"></a> CDockState:: SaveState

状態情報をレジストリまたはに保存するには、この関数を呼び出します。INI ファイル。

```cpp
void SaveState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリ内のキーを指定する、null ではない文字列を指します。

### <a name="remarks"></a>解説

プロファイル名は、アプリケーションののセクションです。INI ファイルまたはコントロールバーの状態情報を含むレジストリ。 `SaveState` では、現在の画面サイズも保存されます。 コントロールバーの情報は、レジストリまたはから取得できます。を使用した INI ファイル `LoadState` 。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
