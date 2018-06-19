---
title: 変更クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockState
- AFXADV/CDockState
- AFXADV/CDockState::Clear
- AFXADV/CDockState::GetVersion
- AFXADV/CDockState::LoadState
- AFXADV/CDockState::SaveState
- AFXADV/CDockState::m_arrBarInfo
dev_langs:
- C++
helpviewer_keywords:
- CDockState [MFC], Clear
- CDockState [MFC], GetVersion
- CDockState [MFC], LoadState
- CDockState [MFC], SaveState
- CDockState [MFC], m_arrBarInfo
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcfbe14743ffff91a4a1749f0394a6deb8f0547a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367439"
---
# <a name="cdockstate-class"></a>変更クラス
いくつかのドッキング コントロール バーの状態を 2 次メモリ (ファイル) で読み込み、アンロード、またはクリアするシリアル化された `CObject` クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockState : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockState::Clear](#clear)|ドッキング状態情報をクリアします。|  
|[CDockState::GetVersion](#getversion)|格納されているのバージョン番号を取得バーの状態。|  
|[CDockState::LoadState](#loadstate)|取得の状態情報をレジストリまたはします。INI ファイルです。|  
|[後](#savestate)|状態情報をレジストリまたは INI ファイルに保存します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockState::m_arrBarInfo](#m_arrbarinfo)|格納されているへのポインターの配列は、それぞれのコントロール バーの 1 つのエントリの状態情報をドッキングします。|  
  
## <a name="remarks"></a>コメント  
 ドッキング状態には、ドッキングされているかどうか、バーの位置とサイズが含まれています。 ドッキング状態を取得する、格納されているときに`CDockState`バーのチェックの位置と、バーが、現在の画面設定で表示されない場合`CDockState`バーの表示されるように配置します。 主な目的`CDockState`を保存するには、その状態を許可するのには、さまざまなコントロール バーの状態全体を保持して、レジストリに、アプリケーションのロードします。INI ファイル、またはの一部としてバイナリ形式で、`CArchive`オブジェクトの内容。  
  
 バーは、任意のドッキング可能なコントロール バー、ツールバー、ステータス バー、またはダイアログ バーを含むです。 `CDockState` オブジェクトは読み取りし、書き込みを使用するファイルと、`CArchive`オブジェクト。  
  
 [CFrameWnd::GetDockState](../../mfc/reference/cframewnd-class.md#getdockstate)フレーム ウィンドウのすべての状態情報が取得`CControlBar`オブジェクトおよび格納に、`CDockState`オブジェクト。 内容を記述することができますし、`CDockState`オブジェクトを持つ記憶域を[Serialize](../../mfc/reference/cobject-class.md#serialize)または[後](#savestate)です。 後で、フレーム ウィンドウのコントロール バーの状態を復元する場合での状態を読み込むことができます`Serialize`または[CDockState::LoadState](#loadstate)を使用して[CFrameWnd::SetDockState](../../mfc/reference/cframewnd-class.md#setdockstate)保存していたを適用するにはフレーム ウィンドウのコントロール バーの状態。  
  
 ドッキング コントロール バーの詳細については、記事を参照してください。[コントロール バー](../../mfc/control-bars.md)、[ツールバー: ドッキング ツールバーとフローティング](../../mfc/docking-and-floating-toolbars.md)、および[フレーム ウィンドウ](../../mfc/frame-windows.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDockState`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="clear"></a>  CDockState::Clear  
 格納されているすべてのドッキング情報をクリアするには、この関数を呼び出して、`CDockState`オブジェクト。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 これが表示されているかどうかや、だけでなく、バーがドッキングされているか、バーのサイズと位置があるかどうかが含まれます。  
  
##  <a name="getversion"></a>  CDockState::GetVersion  
 格納されているのバージョン番号を取得するには、この関数を呼び出すバーの状態。  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>戻り値  
 場合は、1、格納されているバー情報が現在の状態であるバーより古い場合は 2、格納されているバー情報は、現在と同じバーの状態。  
  
### <a name="remarks"></a>コメント  
 バージョンのサポートは、新しい永続的なプロパティを追加しを検出し、以前のバージョンのバーによって作成された永続的な状態を読み込むことできますバーを改訂版を有効します。  
  
##  <a name="loadstate"></a>  CDockState::LoadState  
 レジストリから状態情報を取得するには、この関数を呼び出すか。INI ファイルです。  
  
```  
void LoadState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化ファイルまたは状態情報が格納されている Windows レジストリのキーのセクションの名前を指定する null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 プロファイル名は、アプリケーションのセクションです。INI ファイルまたはバーの状態情報を含むレジストリです。 コントロール バーの状態情報をレジストリに保存することができますか。INI ファイルを`SaveState`です。  
  
##  <a name="m_arrbarinfo"></a>  CDockState::m_arrBarInfo  
 A`CPtrArray`の状態情報が保存される各コントロール バーのストアド コントロール バーの情報へのポインターの配列であるオブジェクトを`CDockState`オブジェクト。  
  
```  
CPtrArray m_arrBarInfo;  
```  
  
##  <a name="savestate"></a>  後  
 状態情報をレジストリに保存するには、この関数を呼び出すか。INI ファイルです。  
  
```  
void SaveState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化ファイルまたは状態情報が格納されている Windows レジストリのキーのセクションの名前を指定する null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 プロファイル名は、アプリケーションのセクションです。INI ファイルまたはレジストリを含むコントロール バーの状態情報。 `SaveState` 現在の画面サイズとも保存されます。 コントロール バーの情報をレジストリから取得することができますか。INI ファイルを`LoadState`です。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

