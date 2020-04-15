---
title: 'テクニカル ノート 28: 状況依存のヘルプのサポート'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 502edc837d7886dd60ab5107fb194c1490a76928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370326"
---
# <a name="tn028-context-sensitive-help-support"></a>テクニカル ノート 28: 状況依存のヘルプのサポート

このノートでは、MFC でヘルプ コンテキスト ID とその他のヘルプの問題を割り当てるための規則について説明します。 状況依存のヘルプ サポートには、Visual C++ で使用できるヘルプ コンパイラが必要です。

> [!NOTE]
> WinHelp を使用した状況依存ヘルプの実装に加えて、MFC では HTML ヘルプの使用もサポートされています。 このサポートと HTML ヘルプによるプログラミングの詳細については、「 [HTML ヘルプ : プログラムの状況依存ヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)」を参照してください。

## <a name="types-of-help-supported"></a>サポートされるヘルプの種類

Windows アプリケーションには、2 種類の状況依存ヘルプが実装されています。 最初に"F1 ヘルプ" と呼ばれるこの場合、現在アクティブなオブジェクトに基づいて適切なコンテキストで WinHelp を起動します。 2つ目は「Shift+F1」モードです。 このモードでは、マウスカーソルがヘルプカーソルに変わり、ユーザーはオブジェクトをクリックします。 その時点で、WinHelp は、ユーザーがクリックしたオブジェクトのヘルプを提供するために起動されます。

マイクロソフト財団クラスは、これらの形式のヘルプの両方を実装します。 さらに、フレームワークは、ヘルプインデックスとヘルプの使用という 2 つの簡単なヘルプ コマンドをサポートしています。

## <a name="help-files"></a>ヘルプ ファイル

マイクロソフト財団のクラスは、1 つのヘルプ ファイルを前提としています。 そのヘルプ ファイルには、アプリケーションと同じ名前とパスが必要です。 たとえば、実行可能ファイルが C:\MyApplication\MyHelp.exe の場合、ヘルプ ファイルは C:\MyApplication\MyHelp.hlp である必要があります。 [CWinApp クラス](../mfc/reference/cwinapp-class.md)の*m_pszHelpFilePath*メンバー変数を通してパスを設定します。

## <a name="help-context-ranges"></a>ヘルプ コンテキスト範囲

MFC の既定の実装では、プログラムがヘルプ コンテキスト ID の割り当てに関するいくつかの規則に従う必要があります。 これらのルールは、特定のコントロールに割り当てられた ID の範囲です。 ヘルプに関連するさまざまなメンバー関数の実装を異なって提供することで、これらの規則をオーバーライドできます。

```
0x00000000 - 0x0000FFFF : user defined
0x00010000 - 0x0001FFFF : commands (menus/command buttons)
0x00010000 + ID_
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)
0x00020000 - 0x0002FFFF : windows and dialogs
0x00020000 + IDR_
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)
0x00030000 - 0x0003FFFF : error messages (based on error string ID)
0x00030000 + IDP_
0x00040000 - 0x0004FFFF : special purpose (non-client areas)
0x00040000 + HitTest area
0x00050000 - 0x0005FFFF : controls (those that are not commands)
0x00040000 + IDW_
```

## <a name="simple-help-commands"></a>シンプルな「ヘルプ」コマンド

Microsoft Foundation クラスによって実装される 2 つの簡単なヘルプ コマンドがあります。

- [ID_HELP_INDEXによって実装されています::オンヘルプインデックス](../mfc/reference/cwinapp-class.md#onhelpindex)

- [ID_HELP_USINGCWinAppによって実装されています::オンヘルプUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

最初のコマンドは、アプリケーションのヘルプ インデックスを表示します。 2 つ目は、WinHelp プログラムの使用に関するユーザー ヘルプを示しています。

## <a name="context-sensitive-help-f1-help"></a>状況依存のヘルプ (F1 ヘルプ)

F1 キーは通常、メイン ウィンドウのアクセラレータ テーブルに配置されたアクセラレータによって ID_HELP ID を持つコマンドに変換されます。 ID_HELP コマンドは、メイン ウィンドウまたはダイアログ ボックスの ID_HELP の ID を持つボタンによって生成される場合もあります。

ID_HELP コマンドの生成方法に関係なく、コマンド ハンドラーに到達するまで、通常のコマンドとしてルーティングされます。 MFC のコマンド ルーティング アーキテクチャの詳細については、[テクニカル ノート 21](../mfc/tn021-command-and-message-routing.md)を参照してください。 アプリケーションでヘルプが有効になっている場合、ID_HELPコマンドは[CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp)によって処理されます。 アプリケーション オブジェクトは、ヘルプ メッセージを受信し、コマンドを適切にルーティングします。 これは、既定のコマンド ルーティングが最も具体的なコンテキストを決定するのに十分ではないため、必要です。

`CWinApp::OnHelp`次の順序で WinHelp を起動しようとします。

1. ヘルプ ID`AfxMessageBox`を使用してアクティブな通話をチェックします。 メッセージ ボックスが現在アクティブな場合、WinHelp はそのメッセージ ボックスに適したコンテキストで起動されます。

1. WM_COMMANDHELP メッセージをアクティブ ウィンドウに送信します。 WinHelp を起動してもそのウィンドウが応答しない場合、メッセージが処理されるか、現在のウィンドウがトップレベル ウィンドウになるまで、同じメッセージがそのウィンドウの先祖に送信されます。

1. メイン ウィンドウにID_DEFAULT_HELPコマンドを送信します。 これにより、既定のヘルプが起動されます。 このコマンドは通常、 に`CWinApp::OnHelpIndex`マップされます。

既定の ID ベース値 (コマンドの場合は 0x10000、ダイアログなどのリソースの場合は 0x20000 など) をグローバルにオーバーライドするには、アプリケーションで[CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp)をオーバーライドする必要があります。

この機能とヘルプ コンテキストの決定方法をオーバーライドするには、WM_COMMANDHELP メッセージを処理する必要があります。 フレームワークが提供するヘルプ ルーティングよりも具体的なヘルプ ルーティングを提供する場合は、現在の MDI 子ウィンドウと同じ深さになります。 また、特定のウィンドウやダイアログに関して、そのオブジェクトの現在の内部状態やダイアログ内のアクティブなコントロールに基づいて、より具体的なヘルプを提供することもできます。

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELPは、ヘルプが要求されたときにアクティブ ウィンドウで受信されるプライベート Windows MFC メッセージです。 ウィンドウはこのメッセージを受信すると、ウィンドウの内部状態`CWinApp::WinHelp`と一致するコンテキストを呼び出す場合があります。

*lParam*<br/>
現在利用可能なヘルプ コンテキストが含まれています。 ヘルプ コンテキストが決定されていない場合は *、lParam*は 0 です。 の実装`OnCommandHelp`では *、lParam*のコンテキスト ID を使用して異なるコンテキストを決定したり、`CWinApp::WinHelp`単に に渡すことができます。

*wParam*<br/>
使用されず、ゼロになります。

関数が`OnCommandHelp`呼び`CWinApp::WinHelp`出した場合は **、TRUE**を返す必要があります。 **TRUE を**返すと、このコマンドを他のクラスや他のウィンドウにルーティングすることが停止します。

## <a name="help-mode-shiftf1-help"></a>ヘルプ モード (Shift + F1 ヘルプ)

これは、状況依存のヘルプの 2 番目の形式です。 通常、このモードは、Shift キーを押しながら F1 キーを押すか、メニューまたはツールバーから入力します。 コマンドとして実装されます (ID_CONTEXT_HELP)。 モーダル ダイアログ ボックスまたはメニューがアクティブな間、メッセージ フィルタ フックは、このコマンドを変換するために使用されません`CWinApp::Run`。

このモードに入ると、アプリケーションが通常その領域に対して独自のカーソル (ウィンドウの周りのサイズ変更の境界など) を表示する場合でも、ヘルプのマウス カーソルがアプリケーションのすべての領域に表示されます。 ユーザーは、マウスまたはキーボードを使用してコマンドを選択できます。 コマンドを実行する代わりに、そのコマンドのヘルプが表示されます。 また、ユーザーは画面上の表示されているオブジェクト (ツールバーのボタンなど) をクリックでき、そのオブジェクトのヘルプが表示されます。 このヘルプ モードは、`CWinApp::OnContextHelp`によって提供されます。

このループの実行中は、メニューにアクセスするキーを除き、キーボード入力はすべて非アクティブになります。 また、ユーザーがアクセラレータ キーを`PreTranslateMessage`押してそのコマンドのヘルプを受け取ることができるように、コマンド変換は引き続き実行されます。

関数内で Shift + F1 ヘルプ モードで実行されてはいけない特定の`CWinApp`変換やアクションが発生している場合は、m_bHelpMode*メンバーを*チェックしてから操作を実行してください。 `PreTranslateMessage` の`CDialog`実装は`PreTranslateMessage`、 を呼`IsDialogMessage`び出す前にこれをチェックします。 これにより、Shift + F1 モードのモードレス ダイアログの "ダイアログ ナビゲーション" キーが無効になります。 さらに、`CWinApp::OnIdle`このループ中に引き続き呼び出されます。

ユーザーがメニューからコマンドを選択すると、そのコマンドのヘルプとして処理されます (WM_COMMANDHELPを通じて、以下を参照)。 ユーザーがアプリケーション ウィンドウの表示領域をクリックすると、クライアント以外のクリックとクライアントのクリックのどちらが行われるかの判断が行われます。 `OnContextHelp`クライアントクリック以外のクリックのマッピングを自動的に処理します。 クライアントのクリックの場合は、クリックされたウィンドウにWM_HELPHITTESTを送信します。 そのウィンドウが 0 以外の値を返す場合、その値はヘルプのコンテキストとして使用されます。 0 を返す`OnContextHelp`場合は、親ウィンドウを試行します (そして、そのウィンドウ、その親ウィンドウ、およびその親などで失敗します)。 ヘルプ コンテキストを特定できない場合、既定では、メイン ウィンドウにID_DEFAULT_HELP コマンドが送信され、その後 (通常は)`CWinApp::OnHelpIndex`にマップされます。

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTESTは、Shift + F1 ヘルプ モードでクリックされたアクティブ ウィンドウが受信する MFC プライベート ウィンドウ メッセージです。 ウィンドウはこのメッセージを受信すると、WinHelp で使用する**DWORD**ヘルプ ID を返します。

LOWORD(lParam) は、マウスがウィンドウのクライアント領域を基準にしてクリックされた X 軸デバイス座標を含みます。

HIWORD(lParam)はY軸の座標を含みます。

*wParam*<br/>
は使用されず、ゼロになります。 戻り値が 0 以外の場合、WinHelp はそのコンテキストで呼び出されます。 戻り値が 0 の場合、親ウィンドウにヘルプが照会されます。

多くの場合、既に使用している可能性のあるヒット テスト コードを利用できます。 WM_HELPHITTESTメッセージの処理`CToolBar::OnHelpHitTest`例については の実装を参照してください (コードは、ボタンとツールヒントで`CControlBar`使用されるヒット テスト コードを活用しています)。

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC アプリケーション ウィザードのサポートとメイク

MFC アプリケーション ウィザードは、ヘルプ ファイル (.cnt ファイルおよび .hpj ファイル) をビルドするために必要なファイルを作成します。 また、Microsoft ヘルプ コンパイラで受け入れられる、あらかじめ作成された .rtf ファイルも含まれています。 多くのトピックは完全ですが、特定のアプリケーションに合わせて変更する必要があるものもあります。

「ヘルプ・マッピング」ファイルの自動作成は、MAKEHM というユーティリティーによってサポートされています。 MAKEHM ユーティリティーは、アプリケーションの RESOURCE を変換できます。H ファイルをヘルプ マッピング ファイルに変換します。 次に例を示します。

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

に翻訳されます:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

この形式はヘルプ コンパイラの機能と互換性があり、コンテキスト ID (右側の数字) とトピック名 (左側のシンボル) がマップされます。

MAKEHM のソース コードは、MFC プログラミング ユーティリティのサンプル[MAKEHM](../overview/visual-cpp-samples.md)にあります。

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードの実行後にヘルプ サポートを追加する

アプリケーションにヘルプを追加する最善の方法は、アプリケーションを作成する前に、MFC アプリケーション ウィザードの [拡張機能] ページで [状況依存のヘルプ] オプションを確認することです。 このように、MFC アプリケーション ウィザードは、ヘルプをサポートするために必要な`CWinApp`メッセージ マップ エントリを -derived クラスに自動的に追加します。

## <a name="help-on-message-boxes"></a>メッセージ ボックスのヘルプ

メッセージ ボックス (アラートとも呼ばれることもあります) の`AfxMessageBox`ヘルプは、Windows API`MessageBox`のラッパーである関数を通じてサポートされます。

の 2 つの`AfxMessageBox`バージョンがあり、1 つは文字列 ID で使用し、もう 1`LPCSTR`つは string へのポインターで使用します ( ):

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

どちらの場合も、オプションのヘルプ ID があります。

最初のケースでは、nIDHelp の既定の値は 0 で、このメッセージ ボックスのヘルプは表示されません。 メッセージ ボックスがアクティブな状態でユーザーが F1 キーを押すと、アプリケーションがヘルプをサポートしていても、ユーザーはヘルプを受け取りません。 これが望ましくない場合は、ヘルプ ID を nIDHelp に提供する必要があります。

2 番目の場合、nIDHelp の既定値は -1 で、ヘルプ ID が nIDPrompt と同じであることを示します。 もちろん、アプリケーションがヘルプ対応の場合にのみヘルプが機能します)。 メッセージ ボックスにヘルプサポートがない場合は、nIDHelp に 0 を指定してください。 メッセージをヘルプに対応させたいが、nIDPrompt とは異なるヘルプ ID を希望する場合は、nIDPrompt とは異なる nIDHelp に正の値を指定するだけです。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
