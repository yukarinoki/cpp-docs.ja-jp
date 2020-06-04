---
title: CWinApp のその他のサービス
ms.date: 11/04/2016
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
ms.openlocfilehash: 1f5abcdab3eda1304879b122acc8072951a0e6c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363904"
---
# <a name="special-cwinapp-services"></a>CWinApp のその他のサービス

メッセージ ループを実行し、アプリケーションを初期化し、その後にクリーンアップする機会を与えることに加えて[、CWinApp](../mfc/reference/cwinapp-class.md)は他のいくつかのサービスを提供します。

## <a name="shell-registration"></a><a name="_core_shell_registration"></a>シェル登録

既定では、MFC アプリケーション ウィザードを使用すると、ファイル エクスプローラーまたはファイル マネージャーでダブルクリックすると、アプリケーションで作成したデータ ファイルを開くことができます。 アプリケーションが MDI アプリケーションで、アプリケーションで作成するファイルの拡張子を指定した場合、MFC アプリケーション ウィザードは[、CWinApp](../mfc/reference/cwinapp-class.md)の`InitInstance`[RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes)および[EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)メンバー関数への呼び出しを、書き込むオーバーライドに追加します。

`RegisterShellFileTypes`は、アプリケーションのドキュメントタイプをファイルエクスプローラまたはファイルマネージャに登録します。 この関数は、Windows が管理する登録データベースにエントリを追加します。 エントリは、各ドキュメントの種類を登録し、ファイルの種類にファイル拡張子を関連付け、アプリケーションを開くコマンド ラインを指定し、その種類のドキュメントを開く動的データ 交換 (DDE) コマンドを指定します。

`EnableShellOpen`アプリケーションがファイル エクスプローラまたはファイル マネージャから DDE コマンドを受け取って、ユーザーが選択したファイルを開くようにして、プロセスを完了します。

この自動登録サポートでは`CWinApp`、アプリケーションに .reg ファイルを出荷したり、特別なインストール作業を行う必要がなくなります。

アプリケーションの GDI+ を初期化する場合[(InitInstance](../mfc/reference/cwinapp-class.md#initinstance)関数で[GdiplusStartup](/windows/win32/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup)を呼び出すことによって)、GDI+ バックグラウンド スレッドを抑制する必要があります。

これを行うには`SuppressBackgroundThread`[、Gdiplus スタートアップ入力](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput)構造体のメンバーを**TRUE**に設定します。 GDI+ バックグラウンド スレッドを抑制する場合`NotificationHook`は`NotificationUnhook`、 と の呼び出しをアプリケーションのメッセージ ループに入って終了する直前に行う必要があります。 これらの呼び出しの詳細については、「 [Gdiplus スタートアップ出力](/windows/win32/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput)」を参照してください。 したがって、呼び出`GdiplusStartup`しの良い場所とフック通知関数は、次に示すように、仮想関数[CWinApp::Run](../mfc/reference/cwinapp-class.md#run)のオーバーライドになります。

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

バックグラウンド GDI+ スレッドを抑制しない場合、メイン ウィンドウが作成される前に、アプリケーションに対して DDE コマンドを早期に発行できます。 シェルによって発行された DDE コマンドは、途中で中止され、エラー メッセージが表示される可能性があります。

## <a name="file-manager-drag-and-drop"></a><a name="_core_file_manager_drag_and_drop"></a>ファイル マネージャードラッグ アンド ドロップ

ファイルマネージャまたはファイルエクスプローラのファイルビューウィンドウからアプリケーションのウィンドウにファイルをドラッグできます。 たとえば、1 つ以上のファイルを MDI アプリケーションのメイン ウィンドウにドラッグして、アプリケーションがファイル名を取得し、それらのファイルの MDI 子ウィンドウを開く場合などに使用できます。

アプリケーションでファイルのドラッグ アンド ドロップを有効にするには、MFC アプリケーション ウィザードは[、CWnd](../mfc/reference/cwnd-class.md)メンバー関数[DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles)をメイン`InitInstance`フレーム ウィンドウの呼び出しを書き込みます。 ドラッグ アンド ドロップ機能を実装しない場合は、その呼び出しを削除できます。

> [!NOTE]
> OLE を使用して、ドキュメント間またはドキュメント内でのデータのドラッグなど、より一般的なドラッグ アンド ドロップ機能を実装することもできます。 詳細については、「 OLE[ドラッグ アンド ドロップ](../mfc/drag-and-drop-ole.md)」を参照してください。

## <a name="keeping-track-of-the-most-recently-used-documents"></a><a name="_core_keeping_track_of_the_most_recently_used_documents"></a>最近使用したドキュメントの追跡

ユーザーがファイルを開いて閉じると、アプリケーション オブジェクトは最近使用した 4 つのファイルを追跡します。 これらのファイルの名前は、[ファイル] メニューに追加され、変更されると更新されます。 フレームワークは、これらのファイル名を、プロジェクトと同じ名前でレジストリまたは .ini ファイルに格納し、アプリケーションの起動時にファイルから読み取ります。 MFC`InitInstance`アプリケーション ウィザードによって作成されるオーバーライドには[、CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数[LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)の呼び出しが含まれており、レジストリまたは .ini ファイルから情報が読み込まれます( 最近使用したファイル名を含む)。

これらのエントリは、次のように格納されます。

- Windows NT、Windows 2000 以降では、レジストリ キーに格納されます。

- Windows 3.x では、値は WIN に格納されます。INI ファイル。

- Windows 95 以降では、値はキャッシュされたバージョンの WIN に格納されます。Ini。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
