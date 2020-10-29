---
title: 'チュートリアル: 従来の Windows デスクトップアプリケーションの作成 (C++)'
description: Visual Studio、C++、および Win32 API を使用して、従来の Windows デスクトップアプリケーションを作成する方法
ms.custom: get-started-article
ms.date: 05/28/2020
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 36991cf98867e7da218f7414d1ea02aab55301a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924228"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>チュートリアル: 従来の Windows デスクトップアプリケーションの作成 (C++)

このチュートリアルでは、Visual Studio で従来の Windows デスクトップアプリケーションを作成する方法について説明します。 作成するアプリケーションの例では、Windows API を使用して "Hello, Windows desktop!" と表示します。 。ウィンドウです。 このチュートリアルで開発したコードは、他の Windows デスクトップ アプリケーションを作成するためのパターンとして使用できます。

Windows API (Win32 API、Windows デスクトップ API、および Windows Classic API とも呼ばれます) は、Windows アプリケーションを作成するための C 言語ベースのフレームワークです。 1980年以降、Windows アプリケーションの作成に使用されてきたため、このようなことはありません。 Windows API に加えて、より高度で使いやすいフレームワークが構築されています。 たとえば、MFC、ATL、.NET framework などです。 C++/WinRT で記述された UWP およびストアアプリの最新の Windows ランタイムコードでも、の下の Windows API を使用します。 Windows API の詳細については、「 [WINDOWS Api Index](/windows/win32/apiindex/windows-api-list)」を参照してください。 Windows アプリケーションを作成する方法は多数ありますが、上記のプロセスは最初のプロセスです。

> [!IMPORTANT]
> 簡潔にするために、一部のコードステートメントはテキストで省略されています。 このドキュメントの最後にある「 [コードをビルド](#build-the-code) する」セクションは、完全なコードを示しています。

## <a name="prerequisites"></a>必須コンポーネント

- Microsoft Windows 7 またはそれ以降のバージョンを稼働しているコンピューター。 最適な開発作業のためには、Windows 10 をお勧めします。

- Visual Studio。 Visual Studio をダウンロードしてインストールする方法について詳しくは、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」をご覧ください。 インストーラーを実行するときに、 **[C++ によるデスクトップ開発]** ワークロードがオンになっていることを確認してください。 Visual Studio をインストールしたときにこのワークロードをインストールしていなくても問題ありません。 インストーラーをもう一度実行して、すぐにインストールできます。

   ![C++ によるデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

- Visual Studio IDE の使用に関する基本事項の理解。 以前に Windows デスクトップ アプリを使ったことがあれば、おそらく問題ありません。 概要については、[Visual Studio IDE の機能ツアー](/visualstudio/ide/visual-studio-ide)に関するページをご覧ください。

- 内容を理解するための、C++ 言語の基本に関する十分な理解。 あまり複雑な作業は行わないので、ご安心ください。

## <a name="create-a-windows-desktop-project"></a>Windows デスクトッププロジェクトを作成する

最初の Windows デスクトッププロジェクトを作成するには、次の手順に従います。 作業中の Windows デスクトップアプリケーションのコードを入力します。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。

::: moniker range="msvc-160"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Visual Studio 2019 で Windows デスクトッププロジェクトを作成するには

1. メイン メニューで、 **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、 **[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. ダイアログの上部で、[ **言語** ] を [ **C++** ] に設定し、[ **プラットフォーム** ] を [ **Windows** ] に設定し、[ **プロジェクトの種類** ] を [ **デスクトップ** ] に設定します。

1. フィルター処理されたプロジェクトの種類の一覧から [ **Windows デスクトップウィザード** ] を選択し、[ **次へ** ] をクリックします。 次のページで、プロジェクトの名前を入力します。たとえば、「 *Desktopapp* 」と入力します。

1. **[作成]** ボタンをクリックしてプロジェクトを作成します。

1. [ **Windows デスクトッププロジェクト** ] ダイアログが表示されるようになりました。 [ **アプリケーションの種類** ] で、[ **デスクトップアプリケーション (.exe)** ] を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **[OK]** を選択して、プロジェクトを作成します。

1. **ソリューションエクスプローラー** で、[ **desktopapp** ] プロジェクトを右クリックし、[ **追加** ]、[ **新しい項目** ] の順に選択します。

   ![Visual Studio 2019 の DesktopApp プロジェクトに新しい項目を追加するユーザーを示す短いビデオ。](../build/media/desktop-app-project-add-new-item-153.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [ **名前** ] ボックスに、ファイルの名前を入力します (たとえば、 *HelloWindowsDesktop* )。 **[追加]** をクリックします。

   ![Visual Studio 2019 の [新しい項目の追加] ダイアログボックスのスクリーンショット (Visual C + + > がインストールされていて、[C + + ファイル] オプションが強調表示されている)](../build/media/desktop-app-add-cpp-file-153.png "アプリケーションプロジェクトへの .cpp ファイルの追加")

これでプロジェクトが作成され、ソースファイルがエディターで開かれます。 続行するには、「 [コードの作成](#create-the-code)」に進んでください。

::: moniker-end

::: moniker range="msvc-150"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Visual Studio 2017 で Windows デスクトッププロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、 **[プロジェクト]** を選択します。

1. [ **新しいプロジェクト** ] ダイアログボックスの左側のウィンドウで、[ **インストール済み** の  >  **Visual C++** ] を展開し、[ **Windows デスクトップ** ] を選択します。 中央のウィンドウで、[ **Windows デスクトップウィザード** ] を選択します。

   [ **名前** ] ボックスに、プロジェクトの名前 (「 *desktopapp* 」など) を入力します。 **[OK]** をクリックします。

   ![Visual Studio 2017 の [新しいプロジェクト] ダイアログボックスがインストールされている状態で、visual C と、[Windows デスクトップ] が選択された >、[Windows デスクトップウィザード] オプションが強調表示されている >、[名前] ボックスに「DesktopApp」と入力した場合のスクリーンショット。](../build/media/desktop-app-new-project-name-153.png "DesktopApp プロジェクトに名前を指定する")

1. [ **Windows デスクトッププロジェクト** ] ダイアログボックスの [ **アプリケーションの種類** ] で、[ **windows アプリケーション (.exe)** ] を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **プリコンパイル済みヘッダー** が選択されていないことを確認します。 **[OK]** を選択して、プロジェクトを作成します。

1. **ソリューションエクスプローラー** で、[ **desktopapp** ] プロジェクトを右クリックし、[ **追加** ]、[ **新しい項目** ] の順に選択します。

   ![Visual Studio 2017 の DesktopApp プロジェクトに新しい項目を追加するユーザーを示す短いビデオ。](../build/media/desktop-app-project-add-new-item-153.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [ **名前** ] ボックスに、ファイルの名前を入力します (たとえば、 *HelloWindowsDesktop* )。 **[追加]** をクリックします。

   ![Visual Studio 2017 の [新しい項目の追加] ダイアログボックスのスクリーンショット (Visual C + + > がインストールされていて、[C + + ファイル] オプションが強調表示されている)](../build/media/desktop-app-add-cpp-file-153.png "アプリケーションプロジェクトへの .cpp ファイルの追加")

これでプロジェクトが作成され、ソースファイルがエディターで開かれます。 続行するには、「 [コードの作成](#create-the-code)」に進んでください。

::: moniker-end

::: moniker range="msvc-140"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Visual Studio 2015 で Windows デスクトッププロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、 **[プロジェクト]** を選択します。

1. [ **新しいプロジェクト** ] ダイアログボックスの左側のウィンドウで、[ **インストールされている**  >  **テンプレート**  >  **Visual C++** ] を展開し、[ **Win32** ] を選択します。 中央のペインで、 **[Win32 プロジェクト]** を選択します。

   [ **名前** ] ボックスに、プロジェクトの名前 (「 *desktopapp* 」など) を入力します。 **[OK]** をクリックします。

   ![Visual Studio 2015 の [新しいプロジェクト] ダイアログボックスがインストールされた > テンプレート > Visual C > プラス + 選択された win32 プロジェクトオプション、[Win32 プロジェクト] オプション、[名前] テキストボックスに表示された DesktopApp のスクリーンショット](../build/media/desktop-app-new-project-name-150.png "DesktopApp プロジェクトに名前を指定する")

1. **Win32 アプリケーションウィザード** の [ **概要** ] ページで、[ **次へ** ] をクリックします。

   ![Win32 アプリケーションでの DesktopApp の作成ウィザードの概要](../build/media/desktop-app-win32-wizard-overview-150.png "Win32 アプリケーションでの DesktopApp の作成ウィザードの概要")

1. [ **アプリケーションの設定** ] ページの [ **アプリケーションの種類** ] で、[ **Windows アプリケーション** ] を選択します。 [ **追加オプション** ] で、[ **プリコンパイル済みヘッダー** ] をオフにし、[ **空のプロジェクト** ] を選択します。 **[完了]** を選択して、プロジェクトを作成します。

1. **ソリューションエクスプローラー** で、[desktopapp] プロジェクトを右クリックし、[ **追加** ]、[ **新しい項目** ] の順に選択します。

   ![Visual Studio 2015 の DesktopApp プロジェクトに新しい項目を追加するユーザーを示す短いビデオ。](../build/media/desktop-app-project-add-new-item-150.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [ **名前** ] ボックスに、ファイルの名前を入力します (たとえば、 *HelloWindowsDesktop* )。 **[追加]** をクリックします。

   ![Visual Studio 2015 の [新しい項目の追加] ダイアログボックスのスクリーンショット (Visual C + + > がインストールされていて、[C + + ファイル] オプションが強調表示されている)](../build/media/desktop-app-add-cpp-file-150.png "アプリケーションプロジェクトへの .cpp ファイルの追加")

これでプロジェクトが作成され、ソースファイルがエディターで開かれます。

::: moniker-end

## <a name="create-the-code"></a>コードを作成する

次に、Visual Studio で Windows デスクトップアプリケーションのコードを作成する方法について説明します。

### <a name="to-start-a-windows-desktop-application"></a>Windows デスクトップ アプリケーションを開始するには

1. すべての C アプリケーションおよび C++ アプリケーションが開始点として関数を持つ必要があるのと同様 `main` に、すべての Windows デスクトップアプリケーションには関数が必要 `WinMain` です。 `WinMain` の構文は、次のとおりです。

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   この関数のパラメーターと戻り値の詳細については、「 [WinMain entry point](/windows/win32/api/winbase/nf-winbase-winmain)」を参照してください。

   > [!NOTE]
   > 、、またはなどの余分な単語は何です `CALLBACK` `HINSTANCE` `_In_` か。 従来の Windows API では、typedef およびプリプロセッサマクロを広範囲にわたって使用して、呼び出し規約、宣言、コンパイラプラグマなど、型の詳細とプラットフォーム固有のコードを抽象化して **`__declspec`** います。 Visual Studio では、IntelliSense の [クイックヒント](/visualstudio/ide/using-intellisense#quick-info) 機能を使用して、これらの typedef とマクロで定義されている内容を確認できます。 目的の単語の上にマウスポインターを移動するか、それを選択して **ctrl** + **K** キー、 **ctrl** + **I** キーを押します。定義を含む小さなポップアップウィンドウが表示されます。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。 多くの場合、パラメーターと戻り値の型は *SAL 注釈* を使用して、プログラミングエラーをキャッチします。 詳細については、「 [SAL 注釈を使用して C/c + + コードの欠陥を減らす](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)」を参照してください。

1. Windows デスクトッププログラムでは、 &lt; windows .h> が必要です。 &lt;tchar.h> はマクロを定義します。 `TCHAR` このマクロは、最終的には、 **`wchar_t`** プロジェクトで UNICODE シンボルが定義されている場合に解決されます。それ以外の場合は、に解決され **`char`** ます。  常に UNICODE が有効な状態でビルドする場合は、TCHAR は不要で、直接だけを使用でき **`wchar_t`** ます。

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. 関数と共に `WinMain` 、すべての Windows デスクトップアプリケーションにもウィンドウプロシージャ関数が必要です。 通常、この関数はという名前です `WndProc` が、好きな名前を付けることができます。 `WndProc` の構文は、次のとおりです。

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   この関数では、 *イベント* が発生したときに、アプリケーションが Windows から受け取る *メッセージ* を処理するコードを記述します。 たとえば、ユーザーがアプリケーションで [OK] ボタンをクリックすると、Windows によってメッセージが送信され、 `WndProc` 適切な処理を実行する関数内にコードを記述することができます。 これは、イベントの *処理* と呼ばれます。 アプリケーションに関連するイベントのみを処理します。

   詳細については、「 [ウィンドウ プロシージャ](/windows/win32/winmsg/window-procedures)」を参照してください。

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 関数に機能を追加するには

1. 関数では、 `WinMain` [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)型の構造体を設定します。 構造体には、ウィンドウに関する情報 (アプリケーションアイコン、ウィンドウの背景色、タイトルバーに表示される名前など) が含まれます。 重要なのは、ウィンドウプロシージャへの関数ポインターが含まれていることです。 一般的な `WNDCLASSEX` 構造体の例を次に示します。

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   上の構造のフィールドの詳細については、「 [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)」を参照してください。

1. `WNDCLASSEX`ウィンドウと、メッセージを送信する方法を認識できるように、を Windows に登録します。 [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) 関数を使用して、ウィンドウ クラス構造体を引数として渡します。 `_T`型を使用するため、マクロが使用され `TCHAR` ます。

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. これで、ウィンドウを作成できます。 [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) 関数を使用します。

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   この関数 `HWND` は、ウィンドウへのハンドルであるを返します。 ハンドルは、Windows が開いているウィンドウを追跡するために使用するポインターに似ています。 詳細については、「 [Windows のデータ型](/windows/win32/WinProg/windows-data-types)」を参照してください。

1. この時点で、ウィンドウは作成されていますが、表示されるように Windows に指示する必要があります。 このコードでは、次の処理を行います。

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   関数をまだ実装していないため、表示されるウィンドウには多くのコンテンツがありません `WndProc` 。 つまり、アプリケーションは、Windows が現在送信しているメッセージをまだ処理していません。

1. メッセージを処理するには、まず、Windows が送信するメッセージをリッスンするメッセージループを追加します。 アプリケーションがメッセージを受信すると、このループによってメッセージが `WndProc` 処理される関数にディスパッチされます。 メッセージ ループのコードは、次のようになります。

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   メッセージ ループ内の構造体と関数の詳細については、「 [MSG](/windows/win32/api/winuser/ns-winuser-msg)」、「 [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage)」、「 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)」、「 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)」を参照してください。

   この段階では、 `WinMain` 関数のコードは次のようになります。

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc 関数に機能を追加するには

1. `WndProc` 関数を有効にしてアプリケーションが受け取るメッセージを処理するために、switch ステートメントを実装します。

   処理する重要なメッセージの1つは、 [WM_PAINT](/windows/win32/gdi/wm-paint) メッセージです。 アプリケーションは、表示されている `WM_PAINT` ウィンドウの一部を更新する必要があるときに、メッセージを受信します。 イベントは、ユーザーがウィンドウの前にウィンドウを移動したときに発生する可能性があります。 アプリケーションは、これらのイベントがいつ発生したかを認識しません。 Windows だけが知っているので、メッセージをアプリに通知 `WM_PAINT` します。 ウィンドウが最初に表示されたら、そのすべてを更新する必要があります。

   `WM_PAINT` メッセージを処理するには、まず [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint)を呼び出して、ウィンドウのテキスト、ボタン、その他のコントロールをレイアウトするためのすべてのロジックを処理し、次に [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint)を呼び出します。 アプリケーションでは、開始呼び出しと終了呼び出しの間のロジックによって、"Hello, Windows desktop!" という文字列が表示されます。 ウィンドウです。 次のコードでは、文字列を表示するために [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) 関数が使用されています。

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC` コードはデバイスコンテキストを示すハンドルであり、ウィンドウのクライアント領域に描画するために使用されます。 `BeginPaint` `EndPaint` クライアント領域で描画を準備して完了するには、関数と関数を使用します。 `BeginPaint` クライアント領域に描画するために使用される表示デバイスコンテキストへのハンドルを返します。 `EndPaint` 描画要求を終了し、デバイスコンテキストを解放します。

1. 通常、アプリケーションは他の多くのメッセージを処理します。 たとえば、ウィンドウが最初に作成されたときに [WM_CREATE](/windows/win32/winmsg/wm-create) 、ウィンドウが閉じられたときに [WM_DESTROY](/windows/win32/winmsg/wm-destroy) ます。 単純でも完成した `WndProc` 関数のコードを次に示します。

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>コードのビルド

お約束したように、作業中のアプリケーションの完全なコードを次に示します。

### <a name="to-build-this-example"></a>この例をビルドするには

1. エディターで *HelloWindowsDesktop* に入力したすべてのコードを削除します。 このコード例をコピーし、 *HelloWindowsDesktop* に貼り付けます。

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 コンパイルの結果は、Visual Studio の [ **出力** ] ウィンドウに表示されます。

   ![DesktopApp プロジェクトをビルドする](../build/media/desktop-app-project-build-150.gif "DesktopApp プロジェクトをビルドする")

1. アプリケーションを実行するには、 **F5** を押します。 "Hello, Windows desktop!" というテキストを含むウィンドウ 画面の左上隅に表示されます。

   ![DesktopApp プロジェクトを実行する](../build/media/desktop-app-project-run-157.PNG "DesktopApp プロジェクトを実行する")

おめでとうございます。 このチュートリアルを完了し、従来の Windows デスクトップアプリケーションをビルドしました。

## <a name="see-also"></a>こちらもご覧ください

[Windows デスクトップアプリケーション](./desktop-applications-visual-cpp.md)
