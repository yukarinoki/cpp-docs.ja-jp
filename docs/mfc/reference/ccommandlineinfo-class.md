---
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
ms.openlocfilehash: 0b4d5e5d253f2eb10388a69286d21e2190826eba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369454"
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
|[コマンドライン情報::Cコマンドライン情報](#ccommandlineinfo)|既定`CCommandLineInfo`のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|個々のパラメーターを解析するには、このコールバックをオーバーライドします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コマンドライン情報::m_bRunAutomated](#m_brunautomated)|コマンド ライン`/Automation`オプションが見つかった場合を示します。|
|[コマンドライン情報::m_bRunEmbedded](#m_brunembedded)|コマンド ライン`/Embedding`オプションが見つかった場合を示します。|
|[コマンドライン情報::m_bShowSplash](#m_bshowsplash)|スプラッシュ スクリーンを表示する必要があるかどうかを示します。|
|[コマンドライン情報::m_nShellCommand](#m_nshellcommand)|処理するシェル・コマンドを示します。|
|[コマンドライン情報::m_strDriverName](#m_strdrivername)|シェル コマンドが [印刷] の場合は、ドライバー名を示します。それ以外の場合は空です。|
|[コマンドライン情報::m_strFileName](#m_strfilename)|開くまたは印刷するファイル名を示します。シェルコマンドが新規または DDE の場合は空です。|
|[コマンドライン情報::m_strPortName](#m_strportname)|シェル コマンドが [印刷] の場合はポート名を示します。それ以外の場合は空です。|
|[コマンドライン情報::m_strPrinterName](#m_strprintername)|シェルコマンドが印刷の場合は、プリンター名を示します。それ以外の場合は空です。|
|[コマンドライン情報::m_strRestartIdentifier](#m_strrestartidentifier)|再起動マネージャーがアプリケーションを再起動した場合の、再起動マネージャーの一意の再起動識別子を示します。|

## <a name="remarks"></a>解説

MFC アプリケーションは通常、そのアプリケーション オブジェクトの[InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)関数に、このクラスのローカル インスタンスを作成します。 このオブジェクトは[CWinApp::Parse コマンドライン](../../mfc/reference/cwinapp-class.md#parsecommandline)に渡され、オブジェクトを埋めるために[ParseParam](#parseparam)を繰り返し呼び出します`CCommandLineInfo`。 その`CCommandLineInfo`後、コマンド ライン引数とフラグを処理するために、オブジェクトが[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)に渡されます。

このオブジェクトを使用して、次のコマンド ライン オプションとパラメーターをカプセル化できます。

|コマンドライン引数|コマンドの実行|
|----------------------------|----------------------|
|*app*|新しいファイル。|
|*アプリ*のファイル名|ファイルを開きます。|
|*アプリ*`/p`のファイル名|ファイルを既定のプリンタに出力します。|
|*アプリ*`/pt`ファイル名プリンター ドライバー ポート|指定したプリンタにファイルを印刷します。|
|*app* `/dde`|起動して DDE コマンドを待機します。|
|*app* `/Automation`|OLE オートメーション サーバーとして起動します。|
|*app* `/Embedding`|埋め込み OLE アイテムを編集する場合は、起動します。|
|*app* `/Register`<br /><br /> *app* `/Regserver`|登録タスクを実行するようにアプリケーションに通知します。|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|登録解除タスクを実行するようにアプリケーションに通知します。|

他のフラグとパラメーター`CCommandLineInfo`値を処理する新しいクラスを派生させます。 新しいフラグを処理するには[、ParseParam](#parseparam)をオーバーライドします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a>コマンドライン情報::Cコマンドライン情報

このコンストラクターは、`CCommandLineInfo`既定値を持つオブジェクトを作成します。

```
CCommandLineInfo();
```

### <a name="remarks"></a>解説

既定では、スプラッシュ スクリーン ( `m_bShowSplash=TRUE`) が表示され、[ファイル] メニューの`m_nShellCommand`[新規作成] コマンド ( **=NewFile**) が実行されます。

アプリケーション フレームワークは、このオブジェクトのデータ メンバーを埋めるために[ParseParam](#parseparam)を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a>コマンドライン情報::m_bRunAutomated

コマンド ライン`/Automation`でフラグが見つかったことを示します。

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>解説

TRUE の場合は、OLE オートメーション サーバーとして起動します。

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a>コマンドライン情報::m_bRunEmbedded

コマンド ライン`/Embedding`でフラグが見つかったことを示します。

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>解説

TRUE の場合、埋め込み OLE アイテムの編集を開始します。

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a>コマンドライン情報::m_bShowSplash

スプラッシュ スクリーンを表示する必要があることを示します。

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>解説

TRUE の場合、起動時にこのアプリケーションのスプラッシュ 画面が表示されます。 [ParseParam](#parseparam)の既定の実装では[、m_nShellCommand](#m_nshellcommand)がに等しい場合、この`CCommandLineInfo::FileNew`データ メンバーを TRUE に設定します。

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a>コマンドライン情報::m_nShellCommand

アプリケーションのこのインスタンスのシェル コマンドを示します。

```
m_nShellCommand;
```

### <a name="remarks"></a>解説

このデータ メンバーの型は、クラスで定義されている次の列挙型です`CCommandLineInfo`。

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

- `CCommandLineInfo::FileNew`コマンド ラインにファイル名が見つからなかったことを示します。

- `CCommandLineInfo::FileOpen`コマンド ラインでファイル名が見つかり、コマンド ラインで次のフラグが見つからなかったことを示`/p``/pt``/dde`します。

- `CCommandLineInfo::FilePrint`コマンド ライン`/p`でフラグが見つかったことを示します。

- `CCommandLineInfo::FilePrintTo`コマンド ライン`/pt`でフラグが見つかったことを示します。

- `CCommandLineInfo::FileDDE`コマンド ライン`/dde`でフラグが見つかったことを示します。

- `CCommandLineInfo::AppRegister``/Register`または`/Regserver`フラグがコマンド ラインで見つかり、アプリケーションが登録を求められたことを示します。

- `CCommandLineInfo::AppUnregister`または`/Unregserver`アプリケーションが`/Unregister`登録解除を求められたことを示します。

- `CCommandLineInfo::RestartByRestartManager`アプリケーションが再起動マネージャーによって再起動されたことを示します。

- `CCommandLineInfo::FileNothing`起動時に新しい MDI 子ウィンドウの表示をオフにします。 アプリケーション ウィザードによって生成された MDI アプリケーションは、起動時に新しい子ウィンドウを表示します。 この機能を無効にするには、アプリケーションが`CCommandLineInfo::FileNothing`[ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)を呼び出すときにシェル コマンドとして使用できます。 `ProcessShellCommand`は、すべての`CWinApp`派生`InitInstance( )`クラスの によって呼び出されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a>コマンドライン情報::m_strDriverName

3 番目の非フラグ パラメーターの値をコマンド ラインに格納します。

```
CString m_strDriverName;
```

### <a name="remarks"></a>解説

このパラメーターは通常、印刷シェル コマンドのプリンター ドライバーの名前です。 [ParseParam](#parseparam)の既定の実装では、`/pt`フラグがコマンド ラインで見つかった場合にのみ、このデータ メンバーが設定されます。

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a>コマンドライン情報::m_strFileName

最初の非フラグ パラメーターの値をコマンド ラインに格納します。

```
CString m_strFileName;
```

### <a name="remarks"></a>解説

通常、このパラメータは開くファイルの名前です。

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a>コマンドライン情報::m_strPortName

4 番目の非フラグ パラメーターの値をコマンド ラインに格納します。

```
CString m_strPortName;
```

### <a name="remarks"></a>解説

このパラメーターは通常、印刷シェル・コマンドのプリンター・ポートの名前です。 [ParseParam](#parseparam)の既定の実装では、`/pt`フラグがコマンド ラインで見つかった場合にのみ、このデータ メンバーが設定されます。

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a>コマンドライン情報::m_strPrinterName

コマンド ラインに 2 番目の非フラグ パラメーターの値を格納します。

```
CString m_strPrinterName;
```

### <a name="remarks"></a>解説

このパラメーターは通常、シェルに印刷コマンドのプリンターの名前です。 [ParseParam](#parseparam)の既定の実装では、`/pt`フラグがコマンド ラインで見つかった場合にのみ、このデータ メンバーが設定されます。

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a>コマンドライン情報::m_strRestartIdentifier

コマンド ラインの一意の再起動識別子。

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>解説

再起動識別子は、アプリケーションの各インスタンスで一意です。

再起動マネージャーがアプリケーションを終了し、アプリケーションを再起動するように構成されている場合、再起動マネージャーは、オプションのパラメーターとして再起動識別子を使用して、コマンド ラインからアプリケーションを実行します。 再起動マネージャーが再起動識別子を使用すると、アプリケーションは、以前に開いたドキュメントを再度開いて、自動保存されたファイルを回復できます。

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a>コマンドライン情報::Pアルセパラム

フレームワークは、コマンド ラインから個々のパラメーターを解析または解釈するために、この関数を呼び出します。 2 番目のバージョンは、Unicode プロジェクトの最初のバージョンと異なります。

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

*pszパラム*<br/>
パラメーターまたはフラグ。

*フラグ*<br/>
*pszParam*がパラメータかフラグかを示します。

*爆発*<br/>
これがコマンド ラインの最後のパラメータまたはフラグかどうかを示します。

### <a name="remarks"></a>解説

[コマンド ライン :Pの](../../mfc/reference/cwinapp-class.md#parsecommandline)各パラメーターまたは`ParseParam`フラグを 1 回呼び出し、引数を*pszParam*に渡します。 パラメータの最初の文字が ' '**-** または '**/** の場合、その文字は削除され *、bFlag*は TRUE に設定されます。 最後のパラメータを解析する場合 *、bLast*は TRUE に設定されます。

この関数の既定の実装では、次の表に`/p`示`/pt`すように`/dde`、 `/Automation`、 `/Embedding`、 、 、および のフラグが認識されます。

|コマンドライン引数|コマンドの実行|
|----------------------------|----------------------|
|*app*|新しいファイル。|
|*アプリ*のファイル名|ファイルを開きます。|
|*アプリ*`/p`のファイル名|ファイルを既定のプリンタに出力します。|
|*アプリ*`/pt`ファイル名プリンター ドライバー ポート|指定したプリンタにファイルを印刷します。|
|*app* `/dde`|起動して DDE コマンドを待機します。|
|*app* `/Automation`|OLE オートメーション サーバーとして起動します。|
|*app* `/Embedding`|埋め込み OLE アイテムを編集する場合は、起動します。|
|*app* `/Register`<br /><br /> *app* `/Regserver`|登録タスクを実行するようにアプリケーションに通知します。|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|登録解除タスクを実行するようにアプリケーションに通知します。|

この情報[は、](#m_brunembedded)m_bRunEmbedded 、 および[m_nShellCommand](#m_nshellcommand) [m_bRunAutomated](#m_brunautomated)に格納されます。 フラグは、スラッシュ ' '**/** またはハイフン '**-** でマークされます。

既定の実装では、最初の非フラグ パラメーター[を m_strFileName](#m_strfilename)に配置します。 フラグの場合、デフォルトの実装では、2 番目、3 番目、および 4 番目の非フラグパラメーターを[それぞれ](#m_strprintername)m_strPrinterName 、 m_strDriverName 、および[m_strPortName](#m_strportname)に置きます。 [m_strDriverName](#m_strdrivername) `/pt`

また、デフォルトの実装では、新しいファイルの場合にのみ[m_bShowSplash](#m_bshowsplash)を TRUE に設定します。 新しいファイルの場合、ユーザーはアプリケーション自体を含むアクションを実行しました。 シェルを使用して既存のファイルを開くなど、その他のケースでは、ユーザー操作はファイルを直接含みます。 ドキュメント中心の観点では、スプラッシュ画面はアプリケーションの起動を通知する必要はありません。

他のフラグ値とパラメーター値を処理するには、派生クラスでこの関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::Pアルセコマンドライン](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::Pロセスシェルコマンド](../../mfc/reference/cwinapp-class.md#processshellcommand)
