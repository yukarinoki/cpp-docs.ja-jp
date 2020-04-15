---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: 5d0f544943cc8584960bb2668ee7ce326547e2fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372316"
---
# <a name="ckeyboardmanager-class"></a>クラス

メイン フレーム ウィンドウおよび子フレーム ウィンドウのショートカット キーのテーブルを管理します。

## <a name="syntax"></a>構文

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[次の操作を行います。](#ckeyboardmanager)|`CKeyboardManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[キープマネージャー::クリーンアップ](#cleanup)|ショートカット キー テーブルをクリアします。|
|[キープマネージャー::既定のアクセラレータを検索します。](#finddefaultaccelerator)|指定したコマンドとウィンドウの既定のショートカット キーを取得します。|
|[キーハンドル](#iskeyhandled)|キーがアクセラレータ テーブルによって処理されるかどうかを判断します。|
|[キープリント可能なマネージャー::IsKeyプリント可能](#iskeyprintable)|文字が印刷可能かどうかを示します。|
|[キープマネージャー::イズショーオールアクセラレータ](#isshowallaccelerators)|メニューにコマンドのすべてのショートカット キーを表示するか、既定のショートカット キーのみを表示するかを示します。|
|[キーマネージャー::ロードステート](#loadstate)|Windows レジストリからショートカット キー テーブルを読み込みます。|
|[キーマネージャー::リセットオール](#resetall)|アプリケーション リソースからショートカット キー テーブルを再読み込みします。|
|[キープステート](#savestate)|ショートカット キーテーブルを Windows レジストリに保存します。|
|[キーキーマネージャー::ショーオールアクセラレータ](#showallaccelerators)|フレームワークがすべてのコマンドのすべてのショートカット キーを表示するか、各コマンドに対して 1 つのショートカット キーを表示するかを指定します。 このメソッドは、関連付けられたショートカット キーが 1 つしかないコマンドには影響しません。|
|[キープマネージャー::翻訳者](#translatechartoupper)|文字をその上のレジスタに変換します。|
|[次の操作を行います。](#updateacceltable)|新しいショートカット キー テーブルを使用して、ショートカット キー テーブルを更新します。|

## <a name="remarks"></a>解説

このクラスのメンバを使用すると、ショートカット キー テーブルを保存して Windows レジストリに読み込み、テンプレートを使用してショートカット キー テーブルを更新し、フレーム ウィンドウ内のコマンドの既定のショートカット キーを見つけることができます。 また、オブジェクトを`CKeyboardManager`使用して、ショートカット キーをユーザーに表示する方法を制御できます。

オブジェクトは手動で`CKeyboardManager`作成しないでください。 アプリケーションのフレームワークによって自動的に作成されます。 ただし、アプリケーションの初期化プロセス中に[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)を呼び出す必要があります。 アプリケーションのキーボード マネージャーへのポインターを取得するには[、CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)を呼び出します。

## <a name="example"></a>例

`CWinAppEx`クラスから`CKeyboardManager`オブジェクトへのポインターを取得する方法と、メニュー コマンドに関連付けられているすべてのショートカット キーを表示する方法を次の例に示します。 このコード スニペットは、[カスタム ページのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxキーボードマネージャー.h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>次の操作を行います。

`CKeyboardManager` オブジェクトを構築します。

```
CKeyboardManager();
```

### <a name="remarks"></a>解説

ほとんどの場合、`CKeyboardManager`直接作成する必要はありません。 既定では、フレームワークは自動的に作成されます。 へのポインターを取得するには`CKeyboardManager`[、CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)を呼び出します。 手動で作成する場合は[、CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)メソッドを使用して初期化する必要があります。

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a>キープマネージャー::クリーンアップ

リソースを`CKeyboardManager`解放し、すべてのショートカット キー マッピングをクリアします。

```
static void CleanUp();
```

### <a name="remarks"></a>解説

ショートカット キーの詳細については、「[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)」を参照してください。

アプリケーションの終了時にフレームワークが自動的に呼び出すため、アプリケーションの終了時にこの関数を呼び出す必要はありません。

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>キープマネージャー::既定のアクセラレータを検索します。

指定したコマンドとウィンドウの既定のショートカット キーを取得します。

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]コマンド ID。

*Str*<br/>
[アウト]`CString`オブジェクトへの参照。

*フレーム*<br/>
[in]フレーム ウィンドウへのポインター。

*ビシスデフォルトフレーム*<br/>
[in]フレーム ウィンドウが既定のフレーム ウィンドウかどうかを指定します。

### <a name="return-value"></a>戻り値

ショートカットが見つかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは *、uiCmd*で指定されたコマンドを検索し、既定のショートカット キーを取得します。 次に、このショートカット キーに関連付けられた文字列を取得し *、str*パラメーターに値を書き込みます。

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>キーハンドル

指定したキーが[CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)によって処理されるかどうかを判断します。

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*nキー*|[in]確認するキー。|
|*fヴィルト*|[in]ショートカット キーの動作を指定します。 使用可能な値のリストについては[、「ACCEL 構造](/windows/win32/api/winuser/ns-winuser-accel)」を参照してください。|
|*フレーム*|[in]フレーム ウィンドウ。 このメソッドは、ショートカット キーがこのフレームで処理されるかどうかを判断します。|
|*ビシスデフォルトフレーム*|[in]*pWndFrame*が既定のフレーム ウィンドウかどうかを示すブール値パラメーター。|

### <a name="return-value"></a>戻り値

ショートカット キーが処理される場合は TRUE。 キーが処理されない場合、または*pWndFrame*が NULL の場合は FALSE。

### <a name="remarks"></a>解説

入力パラメータは、ショートカット キーが*pWndFrame*で処理されるかどうかを判断するために *、nKey*と*fVirt*の両方のアクセラレータ テーブルのエントリと一致する必要があります。

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>キープリント可能なマネージャー::IsKeyプリント可能

文字が印刷可能かどうかを示します。

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Nchar*|[in]このメソッドがチェックする文字。|

### <a name="return-value"></a>戻り値

文字が印刷可能な場合は 0 以外、印刷できない場合は 0 以外の文字を返します。

### <a name="remarks"></a>解説

このメソッドは、[呼](/windows/win32/api/winuser/nf-winuser-getkeyboardstate)び出しが失敗した場合に失敗します。

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>キープマネージャー::イズショーオールアクセラレータ

メニュー コマンドに関連付けられているすべてのショートカット キーを表示するか、既定のショートカット キーのみを表示するかを示します。

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>戻り値

アプリケーションがメニュー コマンドのすべてのショートカット キーを一覧表示する場合は 0 以外の値を指定します。アプリケーションに既定のショートカット キーのみが表示される場合は 0。

### <a name="remarks"></a>解説

アプリケーションは、メニュー バーにメニュー コマンドのショートカット キーを一覧表示します。 関数[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)を使用して、アプリケーションがすべてのショートカット キーを一覧表示するか、既定のショートカット キーだけを表示するかを制御します。

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a>キーマネージャー::ロードステート

Windows レジストリからショートカット キー テーブルを読み込みます。

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]データが`CKeyboardManager`保存されるレジストリ パス。

*デフォルトフレーム*<br/>
[in]既定のウィンドウとして使用するフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

状態が正常に読み込まれた場合は 0 以外、それ以外の場合は 0 以外の場合。

### <a name="remarks"></a>解説

*パラメーターが*NULL の場合、このメソッドは既定のレジストリの場所にデータがあるかどうかを`CKeyboardManager`確認します。 既定のレジストリの場所は[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)で指定されます。 データは、以前にメソッド[CKeyboard マネージャー::SaveState](#savestate)で書き込む必要があります。

既定のウィンドウを指定しない場合は、アプリケーションのメイン フレーム ウィンドウが使用されます。

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a>キーマネージャー::リセットオール

アプリケーション リソースからショートカット キー テーブルを再読み込みします。

```
void ResetAll();
```

### <a name="remarks"></a>解説

この関数は、インスタンスに格納されているショートカット`CKeyboardManager`をクリアします。 その後、アプリケーション リソースからキーボード マネージャーの状態を再ロードします。

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a>キープステート

ショートカット キーテーブルを Windows レジストリに保存します。

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]`CKeyboardManager`状態を保存するためのレジストリ パス。

*デフォルトフレーム*<br/>
[in]既定のウィンドウになるフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

キーボード・マネージャーの状態が正常に保存された場合は 0 以外、それ以外の場合は 0 以外の場合。

### <a name="remarks"></a>解説

*パラメーターが*NULL の場合、このメソッドは`CKeyboardManager`[、CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)で指定された既定の場所に状態を書き込みます。 場所を指定する場合は、後で[CKeyboardManager::LoadState](#loadstate)メソッドを使用してデータを読み込むことができます。

既定のウィンドウを指定しない場合、メイン フレーム ウィンドウが既定のウィンドウとして使用されます。

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>キーキーマネージャー::ショーオールアクセラレータ

メニュー コマンドに関連付けられているすべてのショートカット キーを表示します。

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>パラメーター

*すべてを表示する*<br/>
[in]TRUE の場合は、すべてのショートカット キーが表示されます。 FALSE の場合、最初のショートカット キーのみが表示されます。

*区切り記号*<br/>
[in]ショートカット キーの間に挿入する文字列。 この区切り記号は、ショートカット キーが 1 つしか表示されない場合には無効です。

### <a name="remarks"></a>解説

既定では、コマンドに複数のショートカット キーが関連付けられている場合、最初のショートカット キーのみが表示されます。 この機能を使用すると、すべてのコマンドに関連付けられているすべてのショートカットキーを一覧表示できます。

ショートカット キーは、メニュー バーのコマンドの横に表示されます。 すべてのショートカット キーが表示されている場合は *、lpszDelimiter*によって提供される文字列は、個々のショートカット キーを区切ります。

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>キープマネージャー::翻訳者

文字をその上のレジスタに変換します。

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>パラメーター

*Nchar*<br/>
[in]変換する文字。

### <a name="return-value"></a>戻り値

入力パラメーターの上位レジスターである文字。

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>次の操作を行います。

新しいショートカット キー テーブルを使用して、ショートカット キー テーブルを更新します。

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
[in]ドキュメント テンプレートへのポインター。

*lpAccel*<br/>
[in]新しいショートカット キーへのポインター。

*Nsize*<br/>
[in]新しいショートカット テーブルのサイズ。

*デフォルトフレーム*<br/>
[in]既定のフレーム ウィンドウへのポインター。

*ハッセルニュー*<br/>
[in]新しいショートカット テーブルへのハンドル。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数を使用して、既存のショートカット テーブルを、複数のフレーム ウィンドウ オブジェクトの新しいショートカット キーに置き換えます。 この関数は、指定されたドキュメント テンプレートに接続されているすべてのフレーム ウィンドウ オブジェクトへのアクセスを取得するためのパラメーターとしてドキュメント テンプレートを受け取ります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[::イニトキーボードマネージャー](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)
