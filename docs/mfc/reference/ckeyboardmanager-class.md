---
title: CKeyboardManager クラス
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
ms.openlocfilehash: c953958b3e0112997423376d42b62953b936049a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303608"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager クラス

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
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|`CKeyboardManager` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CKeyboardManager::CleanUp](#cleanup)|ショートカット キーのテーブルをクリアします。|
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|指定されたコマンドおよびウィンドウの既定のショートカット キーを取得します。|
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|アクセラレータ テーブルで、キーが処理されるかどうかを判断します。|
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|文字が印刷可能かどうかを示します。|
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|メニューには、コマンドのすべてのショートカット キーまたは既定のショートカット キーのみが表示されるかどうかを示します。|
|[CKeyboardManager::LoadState](#loadstate)|Windows レジストリから、ショートカット キーのテーブルを読み込みます。|
|[CKeyboardManager::ResetAll](#resetall)|アプリケーション リソースからのショートカット キーのテーブルを再読み込みします。|
|[CKeyboardManager::SaveState](#savestate)|ショートカット キーのテーブルを Windows レジストリに保存します。|
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|フレームワークは、すべてのコマンドのショートカット キーのすべてまたはコマンドごとに 1 つのショートカット キーを表示するかどうかを指定します。 このメソッドは、1 つだけの関連付けられているショートカット キーを持つコマンドには影響しません。|
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|文字を大文字レジスタに変換します。|
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|新しいショートカット キー テーブルのショートカット キーのテーブルを更新します。|

## <a name="remarks"></a>Remarks

このクラスのメンバーを使用すると、保存、Windows レジストリへのショートカット キーのテーブルを読み込むと、テンプレートを使用して、ショートカット キーのテーブルを更新し、フレーム ウィンドウで、コマンドの既定のショートカット キーを検索します。 さらに、`CKeyboardManager`オブジェクトでは、ユーザーのショートカット キーの表示方法を制御することができます。

作成しないようにする、`CKeyboardManager`手動でのオブジェクトします。 アプリケーションのフレームワークによって自動的に作成されます。 ただし、呼び出す必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)アプリケーションの初期化プロセス中にします。 アプリケーションのキーボード マネージャーへのポインターを取得する[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)します。

## <a name="example"></a>例

次の例へのポインターを取得する方法を示します、`CKeyboardManager`オブジェクトから、`CWinAppEx`クラス、およびメニュー コマンドに関連付けられているすべてのショートカット キーを表示する方法。 このコード スニペットの一部、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxkeyboardmanager.h

##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager

`CKeyboardManager` オブジェクトを構築します。

```
CKeyboardManager();
```

### <a name="remarks"></a>Remarks

ほとんどの場合は作成する必要はありません、`CKeyboardManager`直接します。 既定では、フレームワークの 1 つを作成します。 ポインターを取得する、 `CKeyboardManager`、呼び出す[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)します。 いずれかを手動で作成する場合、は、メソッドを使用して初期化する必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)します。

##  <a name="cleanup"></a>  CKeyboardManager::CleanUp

解放、`CKeyboardManager`リソースをすべてのショートカット キーのマッピングをクリアします。

```
static void CleanUp();
```

### <a name="remarks"></a>Remarks

ショートカット キーの詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)します。

フレームワークはアプリケーションの終了時に自動的に呼び出しがあるため、アプリケーションの終了時に、この関数を呼び出す必要はありません。

##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator

指定されたコマンドおよびウィンドウの既定のショートカット キーを取得します。

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]コマンド id。

*str*<br/>
[out]参照を`CString`オブジェクト。

*pWndFrame*<br/>
[in]フレーム ウィンドウへのポインター。

*bIsDefaultFrame*<br/>
[in]フレーム ウィンドウが既定のフレーム ウィンドウであるかどうかを指定します。

### <a name="return-value"></a>戻り値

ショートカットが見つかった場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドで指定されたコマンドを検索*uiCmd*既定のショートカット キーを取得します。 メソッドは、このショートカット キーに関連付けられている文字列を取得しに値を書き込みます、 *str*パラメーター。

##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled

指定したキーが処理するかどうかを決定します、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)します。

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
|*nKey*|[in]チェックするキー。|
|*fVirt*|[in]ショートカット キーの動作を指定します。 使用可能な値の一覧は、次を参照してください。[アクセル構造](/windows/desktop/api/winuser/ns-winuser-tagaccel)します。|
|*pWndFrame*|[in]フレーム ウィンドウです。 このメソッドは、ショートカット キーがこのフレームで処理されるかどうかを判断します。|
|*bIsDefaultFrame*|[in]示すブール値パラメーターかどうか*pWndFrame*は既定のフレーム ウィンドウです。|

### <a name="return-value"></a>戻り値

ショートカット キーが処理される場合は TRUE。 FALSE、キーが処理されない場合、または場合*pWndFrame*は NULL です。

### <a name="remarks"></a>Remarks

入力パラメーターは、アクセラレータ テーブルで両方のエントリと一致する必要があります*nKey*と*fVirt*でショートカット キーが処理されるかどうかを判断する*pWndFrame*します。

##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable

文字が印刷可能かどうかを示します。

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*NChar*|[in]このメソッドをチェックする文字。|

### <a name="return-value"></a>戻り値

0 以外の文字が印刷可能な場合は、0 でない場合。

### <a name="remarks"></a>Remarks

このメソッドへの呼び出しが失敗した[GetKeyboardState](/windows/desktop/api/winuser/nf-winuser-getkeyboardstate)は失敗します。

##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators

メニューにメニュー コマンドに関連付けられているすべてのショートカット キーまたは既定のショートカット キーのみが表示されるかどうかを示します。

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>戻り値

メニュー コマンドのショートカット キーのすべてが一覧表示する場合は 0 以外アプリケーションが既定のショートカット キーのみを表示する場合は 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションは、メニュー バーでメニュー コマンドのショートカット キーを一覧表示します。 関数を使用して[:showallaccelerators](#showallaccelerators)を制御するかどうか、アプリケーションを一覧表示、すべてのショートカット キーまたは既定のショートカット キーを持つユーザーだけです。

##  <a name="loadstate"></a>  CKeyboardManager::LoadState

Windows レジストリから、ショートカット キーのテーブルを読み込みます。

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
[in]レジストリ パスを`CKeyboardManager`データを保存します。

*pDefaultFrame*<br/>
[in]既定のウィンドウとして使用するフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

以外の場合は、状態が正常に読み込まれたか 0 それ以外の場合。

### <a name="remarks"></a>Remarks

場合、 *lpszProfileName*パラメーターが NULL で、このメソッドの既定のレジストリの場所をチェックする`CKeyboardManager`データ。 既定のレジストリの場所がで指定された、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)します。 メソッドを使用して以前データを記述する必要があります[CKeyboardManager::SaveState](#savestate)します。

既定のウィンドウを指定しない場合、アプリケーションのメイン フレーム ウィンドウが使用されます。

##  <a name="resetall"></a>  CKeyboardManager::ResetAll

アプリケーション リソースからのショートカット キーのテーブルを再読み込みします。

```
void ResetAll();
```

### <a name="remarks"></a>Remarks

この関数に格納されているショートカットのクリア、`CKeyboardManager`インスタンス。 アプリケーション リソースからキーボード マネージャーの状態が 再読み込みします。

##  <a name="savestate"></a>  CKeyboardManager::SaveState

ショートカット キーのテーブルを Windows レジストリに保存します。

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
[in]保存するためのレジストリ パス、`CKeyboardManager`状態。

*pDefaultFrame*<br/>
[in]既定のウィンドウになったフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

キーボード マネージャーの状態が正常に保存されている場合は 0 以外。 それ以外の場合は 0。

### <a name="remarks"></a>Remarks

場合、 *lpszProfileName*パラメーターが NULL でこのメソッドは、書き込み、`CKeyboardManager`状態で指定された既定の場所に、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)します。 場所を指定する場合は、後で、メソッドを使用してデータを読み込むことができます[CKeyboardManager::LoadState](#loadstate)します。

既定のウィンドウを指定しない場合は、メイン フレーム ウィンドウを使用して既定のウィンドウとして。

##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators

メニュー コマンドに関連付けられているすべてのショートカット キーを示します。

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>パラメーター

*bShowAll*<br/>
[in]TRUE の場合、すべてのショートカット キーが表示されます。 FALSE の場合、最初のショートカット キーのみが表示されます。

*lpszDelimiter*<br/>
[in]ショートカット キーの間に挿入する文字列。 1 つのショートカット キーが表示されている場合のみ、この区切り記号による影響はありません。

### <a name="remarks"></a>Remarks

既定では、コマンドは、1 つ以上のショートカット キーがそれに関連付けられている場合、最初のショートカット キーのみ表示されます。 この関数では、すべてのコマンドに関連付けられているすべてのショートカット キーを一覧表示することができます。

ショートカット キーは、メニュー バーで、コマンドの横に表示されます。 文字列がによって提供されるすべてのショートカット キーが表示される場合*lpszDelimiter*個々 のショートカット キーを分離します。

##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper

文字を大文字レジスタに変換します。

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>パラメーター

*NChar*<br/>
[in]変換する文字。

### <a name="return-value"></a>戻り値

入力パラメーターの大文字のレジスタにある文字。

##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable

新しいショートカット キー テーブルのショートカット キーのテーブルを更新します。

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

*pTemplate*<br/>
[in]ドキュメント テンプレートへのポインター。

*lpAccel*<br/>
[in]新しいショートカット キーへのポインター。

*nSize*<br/>
[in]新しいショートカットのテーブルのサイズ。

*pDefaultFrame*<br/>
[in]既定のフレーム ウィンドウへのポインター。

*hAccelNew*<br/>
[in]新しいショートカット テーブルへのハンドル。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数を使用して、既存のショートカットの表をいくつかのフレーム ウィンドウ オブジェクトの新しいショートカット キーに置き換えます。 関数は、特定のドキュメント テンプレートに接続されているすべてのフレーム ウィンドウ オブジェクトへのアクセスを取得するパラメーターとして、ドキュメント テンプレートを受け取ります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)
