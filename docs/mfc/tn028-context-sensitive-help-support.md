---
description: '詳細については、「テクニカルノート 28: Context-Sensitive Help Support」を参照してください。'
title: 'テクニカル ノート 28: 状況依存のヘルプのサポート'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 96dd1d4356ac226d9377e14985de46e3d0f680ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215652"
---
# <a name="tn028-context-sensitive-help-support"></a>テクニカル ノート 28: 状況依存のヘルプのサポート

このメモでは、MFC でヘルプコンテキスト Id やその他のヘルプの問題を割り当てるための規則について説明します。 状況依存のヘルプサポートには、Visual C++ で利用できるヘルプコンパイラが必要です。

> [!NOTE]
> WinHelp を使用して状況依存のヘルプを実装するだけでなく、MFC では HTML ヘルプの使用もサポートしています。 このサポートと HTML ヘルプを使用したプログラミングの詳細については、「 [Html ヘルプ: Context-Sensitive プログラムのヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)」を参照してください。

## <a name="types-of-help-supported"></a>サポートされるヘルプの種類

Windows アプリケーションには、2種類の状況依存のヘルプが実装されています。 1つ目は "F1 ヘルプ" と呼ばれ、現在アクティブなオブジェクトに基づいて、適切なコンテキストで WinHelp を起動します。 2つ目は "Shift + F1" モードです。 このモードでは、マウスカーソルがヘルプカーソルに変わり、ユーザーはオブジェクトをクリックし続けます。 その時点で、ユーザーがクリックしたオブジェクトのヘルプを提供する WinHelp が起動されます。

Microsoft Foundation Classes は、これらの形式のヘルプの両方を実装します。 また、フレームワークでは、ヘルプインデックスとヘルプの使用の2つの簡単なヘルプコマンドがサポートされています。

## <a name="help-files"></a>ヘルプ ファイル

Microsoft Foundation classes は、1つのヘルプファイルを想定しています。 ヘルプファイルの名前とパスは、アプリケーションと同じである必要があります。 たとえば、実行可能ファイルが C:\MyApplication\MyHelp.exe 場合は、ヘルプファイルを C:\MyApplication\MyHelp.hlp. する必要があります。 このパスを設定するには、 [CWinApp クラス](../mfc/reference/cwinapp-class.md)の *m_pszHelpFilePath* メンバー変数を使用します。

## <a name="help-context-ranges"></a>ヘルプコンテキスト範囲

MFC の既定の実装では、ヘルプコンテキスト Id の割り当てに関するいくつかの規則に従うプログラムが必要です。 これらのルールは、特定のコントロールに割り当てられた Id の範囲です。 これらの規則をオーバーライドするには、さまざまなヘルプ関連のメンバー関数のさまざまな実装を提供します。

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

## <a name="simple-help-commands"></a>単純な "Help" コマンド

Microsoft Foundation Classes によって実装される次の2つの簡単なヘルプコマンドがあります。

- [CWinApp:: OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)によって実装される ID_HELP_INDEX

- [CWinApp:: OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)によって実装される ID_HELP_USING

最初のコマンドは、アプリケーションのヘルプインデックスを表示します。 2番目の例では、WinHelp プログラムの使用に関するユーザーのヘルプを示しています。

## <a name="context-sensitive-help-f1-help"></a>Context-Sensitive のヘルプ (F1 ヘルプ)

F1 キーは通常、メインウィンドウのアクセラレータテーブルに配置されたアクセラレータによって ID_HELP の ID を持つコマンドに変換されます。 ID_HELP コマンドは、メインウィンドウまたはダイアログボックスに ID_HELP の ID を持つボタンによって生成されることもあります。

ID_HELP コマンドの生成方法に関係なく、コマンドハンドラーに到達するまで、通常のコマンドとしてルーティングされます。 MFC コマンドルーティングアーキテクチャの詳細については、「 [テクニカルノート 21](../mfc/tn021-command-and-message-routing.md)」を参照してください。 アプリケーションでヘルプが有効になっている場合は、ID_HELP コマンドが [CWinApp:: OnHelp](../mfc/reference/cwinapp-class.md#onhelp)によって処理されます。 アプリケーションオブジェクトは、ヘルプメッセージを受信し、適切にコマンドをルーティングします。 これが必要なのは、既定のコマンドルーティングでは、特定のコンテキストを特定するのに十分ではないためです。

`CWinApp::OnHelp` 次の順序で WinHelp を起動しようとします。

1. アクティブな呼び出しに `AfxMessageBox` ヘルプ ID があるかどうかを確認します。 メッセージボックスが現在アクティブになっている場合は、そのメッセージボックスに適したコンテキストで WinHelp が起動されます。

1. WM_COMMANDHELP メッセージをアクティブウィンドウに送信します。 このウィンドウが WinHelp を起動しても応答しない場合は、メッセージが処理されるか、現在のウィンドウがトップレベルウィンドウになるまで、同じメッセージがそのウィンドウの祖先に送信されます。

1. メインウィンドウに ID_DEFAULT_HELP コマンドを送信します。 これにより、既定のヘルプが呼び出されます。 このコマンドは、通常、にマップされ `CWinApp::OnHelpIndex` ます。

既定の ID ベース値 (たとえば、コマンドの場合は0x20000、ダイアログなどのリソースの場合は) をグローバルにオーバーライドするには、アプリケーションで [CWinApp:: WinHelp](../mfc/reference/cwinapp-class.md#winhelp)をオーバーライドする必要があります。

この機能をオーバーライドし、ヘルプコンテキストを決定する方法をオーバーライドするには、WM_COMMANDHELP メッセージを処理する必要があります。 現在の MDI 子ウィンドウと同じように表示されるだけなので、フレームワークよりも具体的なヘルプルーティングを提供できます。 また、特定のウィンドウやダイアログに対して、そのオブジェクトの現在の内部状態やダイアログ内のアクティブコントロールに基づいて、より具体的なヘルプを提供することもできます。

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP は、ヘルプが要求されたときにアクティブウィンドウによって受信される、プライベートな Windows MFC メッセージです。 ウィンドウがこのメッセージを受信すると、 `CWinApp::WinHelp` ウィンドウの内部状態と一致するコンテキストでを呼び出すことができます。

*lParam*<br/>
現在使用可能なヘルプコンテキストを格納します。 ヘルプコンテキストが決定されていない場合、 *lParam* は0になります。 の実装では、 `OnCommandHelp` *lParam* のコンテキスト ID を使用して別のコンテキストを判断したり、に渡したりすることができ `CWinApp::WinHelp` ます。

*wParam*<br/>
は使用されず、は0になります。

関数が `OnCommandHelp` を呼び出す場合は `CWinApp::WinHelp` 、 **TRUE** を返す必要があります。 **TRUE** を返すと、このコマンドを他のクラスや他のウィンドウにルーティングできなくなります。

## <a name="help-mode-shiftf1-help"></a>ヘルプモード (Shift + F1 ヘルプ)

これは、状況依存のヘルプの2番目の形式です。 通常、このモードを入力するには、SHIFT + F1 キーを押すか、メニューまたはツールバーを使用します。 これは、コマンド (ID_CONTEXT_HELP) として実装されます。 モーダルダイアログボックスまたはメニューがアクティブになっている間、メッセージフィルターフックはこのコマンドの変換には使用されないため、このコマンドは、アプリケーションがメインメッセージポンプ () を実行している場合にのみ、ユーザーが使用でき `CWinApp::Run` ます。

このモードを入力すると、アプリケーションのすべての領域に対してヘルプマウスカーソルが表示されます (ウィンドウの周囲のサイズ変更境界など、アプリケーションに通常はその領域のカーソルが表示されます)。 ユーザーは、マウスまたはキーボードを使用してコマンドを選択できます。 コマンドを実行する代わりに、そのコマンドのヘルプが表示されます。 また、ユーザーは、ツールバーのボタンなど、画面上の表示されているオブジェクトをクリックして、そのオブジェクトのヘルプを表示することもできます。 このモードのヘルプは、によって提供され `CWinApp::OnContextHelp` ます。

このループの実行中は、メニューにアクセスするキーを除き、すべてのキーボード入力が非アクティブになります。 また、コマンド変換は、 `PreTranslateMessage` ユーザーがアクセラレータキーを押してそのコマンドのヘルプを受け取ることができるようにするために、でも実行されます。

SHIFT + F1 ヘルプモードでは実行されない特定の翻訳または操作が関数内で発生している場合は `PreTranslateMessage` 、これらの操作を実行する前にの *m_bHelpMode* メンバーを確認する必要があり `CWinApp` ます。 `CDialog`の実装では `PreTranslateMessage` 、を呼び出す前にこれ `IsDialogMessage` をチェックします (たとえば、)。 これにより、SHIFT + F1 モードで、モードレスダイアログの "ダイアログナビゲーション" キーが無効になります。 また、 `CWinApp::OnIdle` はこのループ中にも呼び出されます。

ユーザーがメニューからコマンドを選択した場合は、そのコマンドのヘルプとして処理されます (WM_COMMANDHELP、以下を参照)。 ユーザーが [アプリケーション] ウィンドウの表示領域をクリックした場合、クライアントが非クライアントクリックかクライアントクリックかについて決定が行われます。 `OnContextHelp` クライアントのクリックに対する非クライアントクリックとのマッピングを自動的に処理します。 クライアントがクリックした場合、クリックされたウィンドウに WM_HELPHITTEST が送信されます。 そのウィンドウが0以外の値を返した場合、その値がヘルプのコンテキストとして使用されます。 0が返された場合、は `OnContextHelp` 親ウィンドウを試行します (その親ウィンドウの失敗、親など)。 ヘルプコンテキストを特定できない場合、既定では、メインウィンドウに ID_DEFAULT_HELP コマンドが送信されます。これは (通常は) にマップされ `CWinApp::OnHelpIndex` ます。

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST は、SHIFT + F1 ヘルプモードでクリックされたアクティブウィンドウによって受信される MFC プライベート windows メッセージです。 ウィンドウがこのメッセージを受信すると、WinHelp によって使用される **DWORD** ヘルプ ID を返します。

LOWORD (lParam) には、ウィンドウのクライアント領域に対してマウスがクリックされた位置の X 軸のデバイス座標が含まれています。

HIWORD (lParam) に Y 軸座標が含まれています。

*wParam*<br/>
は使用されず、は0になります。 戻り値が0以外の場合は、そのコンテキストで WinHelp が呼び出されます。 戻り値が0の場合、親ウィンドウにはヘルプが照会されます。

多くの場合、既に存在する可能性のあるヒットテストコードを活用できます。 WM_HELPHITTEST メッセージの処理の例については、の実装を参照してください `CToolBar::OnHelpHitTest` (のボタンとツールヒントで使用されるヒットテストコードを活用するコード `CControlBar` )。

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC アプリケーションウィザードのサポートと MAKEHM

MFC アプリケーションウィザードでは、ヘルプファイル (.cnt および .hpj ファイル) をビルドするために必要なファイルが作成されます。 また、Microsoft ヘルプコンパイラで受け入れられる多数の事前に構築された .rtf ファイルも含まれています。 トピックの多くは完了していますが、特定のアプリケーションで変更が必要になる場合があります。

"ヘルプマッピング" ファイルの自動作成は、MAKEHM と呼ばれるユーティリティによってサポートされています。 MAKEHM ユーティリティは、アプリケーションのリソースを変換できます。H ファイルをヘルプマッピングファイルに変換します。 次に例を示します。

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

はに変換されます。

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

この形式は、ヘルプコンパイラのファシリティと互換性があります。これにより、コンテキスト Id (右側の数値) がトピック名 (左側の記号) にマップされます。

MAKEHM のソースコードについては、MFC プログラミングユーティリティのサンプル [MAKEHM](../overview/visual-cpp-samples.md)を参照してください。

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC アプリケーションウィザードを実行した後のヘルプサポートの追加

アプリケーションにヘルプを追加する最善の方法は、アプリケーションを作成する前に、MFC アプリケーションウィザードの [高度な機能] ページで [状況依存のヘルプ] オプションをチェックすることです。 これにより、MFC アプリケーションウィザードでは、ヘルプをサポートするために必要なメッセージマップエントリがの派生クラスに自動的に追加され `CWinApp` ます。

## <a name="help-on-message-boxes"></a>メッセージボックスに関するヘルプ

メッセージボックス (アラートとも呼ばれます) のヘルプは、 `AfxMessageBox` WINDOWS API のラッパーである関数によってサポートされてい `MessageBox` ます。

の2つのバージョンがあり `AfxMessageBox` ます。1つは文字列 ID で使用し、もう1つは string () へのポインターと共に使用し `LPCSTR` ます。

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

どちらの場合も、オプションのヘルプ ID があります。

最初のケースでは、nIDHelp の既定値は0です。これは、このメッセージボックスのヘルプがないことを示します。 ユーザーが F1 キーを押しているときに、メッセージボックスがアクティブである場合、ユーザーはヘルプを受信しません (アプリケーションがヘルプをサポートしている場合でも)。 これが望ましくない場合は、nIDHelp のヘルプ ID を指定する必要があります。

2番目のケースでは、nIDHelp の既定値は-1 です。これは、ヘルプ ID が nIDPrompt と同じであることを示します。 ヘルプは、アプリケーションがヘルプが有効な場合にのみ機能します。 メッセージボックスにヘルプサポートが表示されないようにする場合は、nIDHelp に0を指定する必要があります。 メッセージを有効にする必要があるのに、nIDPrompt とは異なるヘルプ ID を使用する場合は、nIDPrompt とは異なる nIDHelp に正の値を指定するだけです。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
