---
description: '詳細情報: CCommandLineInfo クラス'
title: CCommandLineInfo クラス
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 4c26ae86608725caa61ad4d1077bed01a3f40385
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227924"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo クラス

アプリケーション起動時のコマンド ライン解析を補助します。

## <a name="syntax"></a>構文

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|既定のオブジェクトを構築 `CCommandLineInfo` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|個々のパラメーターを解析するには、このコールバックをオーバーライドします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CCommandLineInfo:: m_bRunAutomated](#m_brunautomated)|コマンドラインオプションが見つかったことを示し `/Automation` ます。|
|[CCommandLineInfo:: m_bRunEmbedded](#m_brunembedded)|コマンドラインオプションが見つかったことを示し `/Embedding` ます。|
|[CCommandLineInfo:: m_bShowSplash](#m_bshowsplash)|スプラッシュスクリーンを表示する必要があるかどうかを示します。|
|[CCommandLineInfo:: m_nShellCommand](#m_nshellcommand)|処理するシェルコマンドを示します。|
|[CCommandLineInfo:: m_strDriverName](#m_strdrivername)|シェルコマンドがに印刷される場合のドライバー名を示します。それ以外の場合は空です。|
|[CCommandLineInfo:: m_strFileName](#m_strfilename)|開くまたは印刷するファイルの名前を示します。シェルコマンドが New または DDE の場合は空です。|
|[CCommandLineInfo:: m_strPortName](#m_strportname)|シェルコマンドがに出力される場合のポート名を示します。それ以外の場合は空です。|
|[CCommandLineInfo:: m_strPrinterName](#m_strprintername)|シェルコマンドがに印刷される場合のプリンター名を示します。それ以外の場合は空です。|
|[CCommandLineInfo:: m_strRestartIdentifier](#m_strrestartidentifier)|再起動マネージャーがアプリケーションを再起動した場合の、再起動マネージャーの一意の再起動識別子を示します。|

## <a name="remarks"></a>解説

通常、MFC アプリケーションでは、そのアプリケーションオブジェクトの [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 関数でこのクラスのローカルインスタンスを作成します。 次に、このオブジェクトが [CWinApp::P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline)に渡されます。この場合、オブジェクトを埋めるために [ParseParam](#parseparam) を繰り返し呼び出します `CCommandLineInfo` 。 `CCommandLineInfo`次に、オブジェクトを[CWinApp::P rocessshellcommand](../../mfc/reference/cwinapp-class.md#processshellcommand)に渡して、コマンドラインの引数とフラグを処理します。

このオブジェクトを使用して、次のコマンドラインオプションとパラメーターをカプセル化できます。

|コマンドライン引数|実行されたコマンド|
|----------------------------|----------------------|
|*app*|新しいファイル。|
|*アプリ* ファイル名|ファイルを開きます。|
|*アプリ* `/p` /db|ファイルを既定のプリンターに印刷します。|
|*アプリ* `/pt` ファイル名プリンタードライバーのポート|指定したプリンターにファイルを印刷します。|
|*アプリ*`/dde`|起動時に DDE コマンドを待機します。|
|*アプリ*`/Automation`|OLE オートメーションサーバーとして起動します。|
|*アプリ*`/Embedding`|埋め込み OLE 項目の編集を開始します。|
|*アプリ*`/Register`<br /><br /> *アプリ*`/Regserver`|登録タスクを実行するようにアプリケーションに通知します。|
|*アプリ*`/Unregister`<br /><br /> *アプリ*`/Unregserver`|登録解除タスクを実行するようにアプリケーションに通知します。|

から新しいクラスを派生させ、 `CCommandLineInfo` 他のフラグとパラメーター値を処理します。 新しいフラグを処理するには、 [ParseParam](#parseparam) をオーバーライドします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a> CCommandLineInfo::CCommandLineInfo

このコンストラクターは、 `CCommandLineInfo` 既定値を使用してオブジェクトを作成します。

```
CCommandLineInfo();
```

### <a name="remarks"></a>解説

既定では、スプラッシュスクリーン () を表示し、[ `m_bShowSplash=TRUE` ファイル] メニュー ( `m_nShellCommand` **= NewFile**) で新しいコマンドを実行します。

アプリケーションフレームワークは、このオブジェクトのデータメンバーを埋めるために [ParseParam](#parseparam) を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a> CCommandLineInfo:: m_bRunAutomated

は、 `/Automation` コマンドラインでフラグが見つかったことを示します。

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>解説

TRUE の場合、これは OLE オートメーションサーバーとして起動することを意味します。

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a> CCommandLineInfo:: m_bRunEmbedded

は、 `/Embedding` コマンドラインでフラグが見つかったことを示します。

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>解説

TRUE の場合は、埋め込み OLE 項目の編集を開始します。

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a> CCommandLineInfo:: m_bShowSplash

スプラッシュスクリーンが表示されることを示します。

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>解説

TRUE の場合、起動時にこのアプリケーションのスプラッシュスクリーンが表示されることを意味します。 [ParseParam](#parseparam)の既定の実装では、 [m_nShellCommand](#m_nshellcommand)がに等しい場合、このデータメンバーは TRUE に設定され `CCommandLineInfo::FileNew` ます。

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a> CCommandLineInfo:: m_nShellCommand

アプリケーションのこのインスタンスのシェルコマンドを示します。

```
m_nShellCommand;
```

### <a name="remarks"></a>解説

このデータメンバーの型は、クラスで定義されている次の列挙型です `CCommandLineInfo` 。

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

これらの値の簡単な説明については、次の一覧を参照してください。

- `CCommandLineInfo::FileNew` コマンドラインでファイル名が見つからなかったことを示します。

- `CCommandLineInfo::FileOpen`は、コマンドラインでファイル名が検出され、コマンドラインで、、のいずれのフラグも見つからなかったことを `/p` 示します。 `/pt` `/dde`

- `CCommandLineInfo::FilePrint` は、 `/p` コマンドラインでフラグが見つかったことを示します。

- `CCommandLineInfo::FilePrintTo` は、 `/pt` コマンドラインでフラグが見つかったことを示します。

- `CCommandLineInfo::FileDDE` は、 `/dde` コマンドラインでフラグが見つかったことを示します。

- `CCommandLineInfo::AppRegister``/Register`またはフラグが `/Regserver` コマンドラインで見つかったため、アプリケーションが登録を要求されたことを示します。

- `CCommandLineInfo::AppUnregister``/Unregister`またはアプリケーションが `/Unregserver` 登録解除を要求されたことを示します。

- `CCommandLineInfo::RestartByRestartManager` アプリケーションが再起動マネージャーによって再起動されたことを示します。

- `CCommandLineInfo::FileNothing` 起動時に新しい MDI 子ウィンドウの表示をオフにします。 仕様により、アプリケーションウィザードで生成された MDI アプリケーションは、起動時に新しい子ウィンドウを表示します。 この機能を無効にするために、アプリケーションは `CCommandLineInfo::FileNothing` [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)を呼び出すときに、シェルコマンドとしてを使用できます。 `ProcessShellCommand` は、 `InitInstance( )` すべての派生クラスのによって呼び出され `CWinApp` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a> CCommandLineInfo:: m_strDriverName

3番目のフラグ以外のパラメーターの値をコマンドラインに格納します。

```
CString m_strDriverName;
```

### <a name="remarks"></a>解説

通常、このパラメーターは、Print To shell コマンドのプリンタードライバーの名前です。 [ParseParam](#parseparam)の既定の実装では、このデータメンバーは、 `/pt` コマンドラインでフラグが見つかった場合にのみ設定されます。

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a> CCommandLineInfo:: m_strFileName

最初のフラグ以外のパラメーターの値をコマンドラインに格納します。

```
CString m_strFileName;
```

### <a name="remarks"></a>解説

このパラメーターは、通常、開くファイルの名前です。

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a> CCommandLineInfo:: m_strPortName

4番目のフラグ以外のパラメーターの値をコマンドラインに格納します。

```
CString m_strPortName;
```

### <a name="remarks"></a>解説

通常、このパラメーターは、Print To shell コマンドのプリンターポートの名前です。 [ParseParam](#parseparam)の既定の実装では、このデータメンバーは、 `/pt` コマンドラインでフラグが見つかった場合にのみ設定されます。

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a> CCommandLineInfo:: m_strPrinterName

2番目の非フラグパラメーターの値をコマンドラインに格納します。

```
CString m_strPrinterName;
```

### <a name="remarks"></a>解説

通常、このパラメーターは Print To shell コマンドのプリンターの名前です。 [ParseParam](#parseparam)の既定の実装では、このデータメンバーは、 `/pt` コマンドラインでフラグが見つかった場合にのみ設定されます。

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a> CCommandLineInfo:: m_strRestartIdentifier

コマンドライン上の一意の再起動識別子。

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>解説

再起動識別子は、アプリケーションの各インスタンスに対して一意です。

再起動マネージャーがアプリケーションを終了し、再起動するように構成されている場合、再起動マネージャーは、再起動識別子を省略可能なパラメーターとしてコマンドラインからアプリケーションを実行します。 再起動マネージャーが再起動識別子を使用すると、アプリケーションは、前に開いていたドキュメントを再び開いて、自動保存されたファイルを回復することができます。

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a> CCommandLineInfo::P arseParam

フレームワークは、コマンドラインから個々のパラメーターを解析/解釈するために、この関数を呼び出します。 2番目のバージョンは、Unicode プロジェクトの最初のバージョンとは異なります。

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>パラメーター

*pszParam*<br/>
パラメーターまたはフラグ。

*bFlag*<br/>
*Pszparam* がパラメーターであるかフラグであるかを示します。

*爆風*<br/>
これがコマンドラインの最後のパラメーターまたはフラグであるかどうかを示します。

### <a name="remarks"></a>解説

[CWinApp::P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline) `ParseParam` は、引数を *pszparam* に渡して、コマンドラインでパラメーターまたはフラグごとに1回を呼び出します。 パラメーターの最初の文字が ' ' または ' ' の場合は、 **-** **/** それが削除され、 *BFLAG* が TRUE に設定されます。 最後のパラメーターを解析するときに、 *ブラスト* は TRUE に設定されます。

この関数の既定の実装では `/p` 、 `/pt` 次の `/dde` `/Automation` `/Embedding` 表に示すように、、、、、およびの各フラグが認識されます。

|コマンドライン引数|実行されたコマンド|
|----------------------------|----------------------|
|*app*|新しいファイル。|
|*アプリ* ファイル名|ファイルを開きます。|
|*アプリ* `/p` /db|ファイルを既定のプリンターに印刷します。|
|*アプリ* `/pt` ファイル名プリンタードライバーのポート|指定したプリンターにファイルを印刷します。|
|*アプリ*`/dde`|起動時に DDE コマンドを待機します。|
|*アプリ*`/Automation`|OLE オートメーションサーバーとして起動します。|
|*アプリ*`/Embedding`|埋め込み OLE 項目の編集を開始します。|
|*アプリ*`/Register`<br /><br /> *アプリ*`/Regserver`|登録タスクを実行するようにアプリケーションに通知します。|
|*アプリ*`/Unregister`<br /><br /> *アプリ*`/Unregserver`|登録解除タスクを実行するようにアプリケーションに通知します。|

この情報は [m_bRunAutomated](#m_brunautomated)、 [m_bRunEmbedded](#m_brunembedded)、および [m_nShellCommand](#m_nshellcommand)に格納されます。 フラグは、スラッシュ ' **/** ' またはハイフン ' ' でマークされてい **-** ます。

既定の実装では、最初の非フラグパラメーターが [m_strFileName](#m_strfilename)に配置されます。 フラグの場合、既定の実装では、 `/pt` 2 番目、3番目、および4番目の非フラグパラメーターが [m_strPrinterName](#m_strprintername)、 [m_strDriverName](#m_strdrivername)、および [m_strPortName](#m_strportname)にそれぞれ配置されます。

また、既定の実装では、新しいファイルの場合にのみ [m_bShowSplash](#m_bshowsplash) が TRUE に設定されます。 新しいファイルの場合、ユーザーはアプリケーション自体に関連するアクションを実行しています。 他のケースでは、シェルを使用して既存のファイルを開くこともできますが、ユーザーの操作にはファイルが直接含まれます。 ドキュメント中心の観点では、スプラッシュスクリーンはアプリケーションの起動を通知する必要はありません。

他のフラグとパラメーター値を処理するには、派生クラスでこの関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::P rocessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)
