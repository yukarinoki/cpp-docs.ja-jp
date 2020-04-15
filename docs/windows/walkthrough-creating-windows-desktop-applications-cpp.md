---
title: 'チュートリアル: 従来の Windows デスクトップ アプリケーション (C++) を作成します。'
description: Visual Studio、C++、および Win32 API を使用して、従来の最小限の Windows デスクトップ アプリケーションを作成する方法
ms.custom: get-started-article
ms.date: 11/03/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: da74778e79a08dd3ed2b5be0675981425264bdc0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351847"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>チュートリアル: 従来の Windows デスクトップ アプリケーション (C++) を作成します。

このチュートリアルでは、Visual Studio で従来の Windows デスクトップ アプリケーションを作成する方法を示します。 作成するアプリケーションの例では、Windows API を使用して "こんにちは、 Windows デスクトップ" を表示します。 。ウィンドウです。 このチュートリアルで開発したコードは、他の Windows デスクトップ アプリケーションを作成するためのパターンとして使用できます。

Windows API (Win32 API、Windows デスクトップ API、および Windows クラシック API とも呼ばれます) は、Windows アプリケーションを作成するための C 言語ベースのフレームワークです。 それは1980年代から存在しており、何十年もの間、Windowsアプリケーションを作成するために使用されてきました。 Windows API の上に、より高度でプログラムしやすいフレームワークが構築されています。 たとえば、MFC、ATL、.NET フレームワークなどです。 C++/WinRT で記述された UWP アプリとストア アプリの最新の Windows ランタイム コードでも、その下の Windows API が使用されています。 Windows API の詳細については、「 [Windows API インデックス](/windows/win32/apiindex/windows-api-list)」を参照してください。 Windows アプリケーションを作成する方法は多数ありますが、上記のプロセスが最初のプロセスでした。

> [!IMPORTANT]
> 簡潔にするために、テキストで一部のコード ステートメントが省略されています。 このドキュメント[の最後にある「コードのビルド](#build-the-code)」セクションでは、完全なコードを示します。

## <a name="prerequisites"></a>前提条件

- Microsoft Windows 7 またはそれ以降のバージョンを稼働しているコンピューター。 最適な開発作業のためには、Windows 10 をお勧めします。

- Visual Studio。 Visual Studio をダウンロードしてインストールする方法について詳しくは、「[Visual Studio のインストール](/visualstudio/install/install-visual-studio)」をご覧ください。 インストーラーを実行するときに、**[C++ によるデスクトップ開発]** ワークロードがオンになっていることを確認してください。 Visual Studio をインストールしたときにこのワークロードをインストールしていなくても問題ありません。 インストーラーをもう一度実行して、すぐにインストールできます。

   ![C++ によるデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ によるデスクトップ開発")

- Visual Studio IDE の使用に関する基本事項の理解。 以前に Windows デスクトップ アプリを使ったことがあれば、おそらく問題ありません。 概要については、[Visual Studio IDE の機能ツアー](/visualstudio/ide/visual-studio-ide)に関するページをご覧ください。

- 内容を理解するための、C++ 言語の基本に関する十分な理解。 あまり複雑な作業は行わないので、ご安心ください。

## <a name="create-a-windows-desktop-project"></a>Windows デスクトップ プロジェクトを作成する

最初の Windows デスクトップ プロジェクトを作成するには、次の手順を実行します。 作業している Windows デスクトップ アプリケーションのコードを入力します。 Visual Studio の優先バージョンのドキュメントを表示するには、**バージョン**セレクター コントロールを使用します。 このページの目次の上部に表示されます。

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Windows デスクトップ プロジェクトを作成するには

1. メイン メニューで、**[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択して、**[新しいプロジェクトの作成]** ダイアログ ボックスを開きます。

1. ダイアログの上部で、[**言語**] を **[C++]** に設定し、[**プラットフォーム**] を **[Windows]** に設定し、[**プロジェクトの種類**] を **[デスクトップ]** に設定します。

1. フィルタ処理されたプロジェクトの種類の一覧から **、[Windows デスクトップ ウィザード**] を選択し、[**次へ**] を選択します。 次のページで、プロジェクトの名前を*入力します。*

1. **[作成]** ボタンをクリックしてプロジェクトを作成します。

1. **[Windows デスクトップ プロジェクト**] ダイアログ ボックスが表示されます。 [**アプリケーションの種類**] で、[**デスクトップ アプリケーション (.exe)]** を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **[OK] を**選択してプロジェクトを作成します。

1. **ソリューション エクスプローラー**で**DesktopApp**プロジェクトを右クリックし、[**追加**] をポイントして、[**新しい項目**] をクリックします。

   ![新しい項目を DesktopApp プロジェクトに追加する](../build/media/desktop-app-project-add-new-item-153.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [**名前**] ボックスに、ファイルの名前を*入力します。* [**追加 ]** をクリックします。

   ![.cpp ファイルを DesktopApp プロジェクトに追加する](../build/media/desktop-app-add-cpp-file-153.png ".cpp ファイルを DesktopApp プロジェクトに追加する")

これでプロジェクトが作成され、ソース ファイルがエディタで開きます。 続行するには、コード[の作成](#create-the-code)に進みます。

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>2017 年の Windows デスクトップ プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、**[プロジェクト]** を選択します。

1. [**新しいプロジェクト**] ダイアログ ボックスの左ペインで **、[インストールされている** > **Visual C++]** を展開し **、[Windows デスクトップ**] を選択します。 中央のウィンドウで **、[Windows デスクトップ ウィザード**] を選択します。

   [**名前**] ボックスに、プロジェクトの*名前を入力*します。 **[OK] をクリック**します。

   ![デスクトップ アプリケーション プロジェクトに名前を付ける](../build/media/desktop-app-new-project-name-153.png "デスクトップ アプリケーション プロジェクトに名前を付ける")

1. [Windows**デスクトップ プロジェクト**] ダイアログの [アプリケーションの**種類**] で **、[Windows アプリケーション (.exe)]** を選択します。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 **[プリコンパイル済みヘッダー** ] が選択されていないことを確認します。 **[OK] を**選択してプロジェクトを作成します。

1. **ソリューション エクスプローラー**で**DesktopApp**プロジェクトを右クリックし、[**追加**] をポイントして、[**新しい項目**] をクリックします。

   ![新しい項目を DesktopApp プロジェクトに追加する](../build/media/desktop-app-project-add-new-item-153.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [**名前**] ボックスに、ファイルの名前を*入力します。* [**追加 ]** をクリックします。

   ![.cpp ファイルを DesktopApp プロジェクトに追加する](../build/media/desktop-app-add-cpp-file-153.png ".cpp ファイルを DesktopApp プロジェクトに追加する")

これでプロジェクトが作成され、ソース ファイルがエディタで開きます。 続行するには、コード[の作成](#create-the-code)に進みます。

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Windows デスクトップ プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、**[プロジェクト]** を選択します。

1. [**新しいプロジェクト**] ダイアログ ボックスの左側のウィンドウで、[**インストールされている** > **テンプレート** > **Visual C++]** を展開し **、[Win32]** を選択します。 中央のペインで、 **[Win32 プロジェクト]** を選択します。

   [**名前**] ボックスに、プロジェクトの*名前を入力*します。 **[OK] をクリック**します。

   ![デスクトップ アプリケーション プロジェクトに名前を付ける](../build/media/desktop-app-new-project-name-150.png "デスクトップ アプリケーション プロジェクトに名前を付ける")

1. **Win32 アプリケーション ウィザード**の [**概要**] ページで、[**次へ**] をクリックします。

   ![Win32 アプリケーション ウィザードでデスクトップ アプリを作成するの概要](../build/media/desktop-app-win32-wizard-overview-150.png "Win32 アプリケーション ウィザードでデスクトップ アプリを作成するの概要")

1. [**アプリケーションの設定] ページ**の [**アプリケーションの種類**] で **、[Windows アプリケーション**] を選択します。 [**追加オプション**] の [**プリコンパイル済みヘッダー**] チェック ボックスをオフにし、[**空のプロジェクト**] を選択します。 [**完了] を**選択してプロジェクトを作成します。

1. **ソリューション エクスプローラー**で DesktopApp プロジェクトを右クリックし、[**追加**] をポイントして、[**新しい項目**] をクリックします。

   ![新しい項目を DesktopApp プロジェクトに追加する](../build/media/desktop-app-project-add-new-item-150.gif "新しい項目を DesktopApp プロジェクトに追加する")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 [**名前**] ボックスに、ファイルの名前を*入力します。* [**追加 ]** をクリックします。

   ![.cpp ファイルを DesktopApp プロジェクトに追加する](../build/media/desktop-app-add-cpp-file-150.png ".cpp ファイルを DesktopApp プロジェクトに追加する")

これでプロジェクトが作成され、ソース ファイルがエディタで開きます。

::: moniker-end

## <a name="create-the-code"></a>コードを作成する

次に、Visual Studio で Windows デスクトップ アプリケーションのコードを作成する方法について説明します。

### <a name="to-start-a-windows-desktop-application"></a>Windows デスクトップ アプリケーションを開始するには

1. すべての C アプリケーションと C++ アプリケーションが`main`、その開始点として機能を持っている必要があるのと`WinMain`同様に、すべての Windows デスクトップ アプリケーションには関数が必要です。 `WinMain` の構文は、次のとおりです。

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   この関数のパラメーターと戻り値については、「 [WinMain エントリ ポイント](/windows/win32/api/winbase/nf-winbase-winmain)」を参照してください。

   > [!NOTE]
   > や`CALLBACK`、や`HINSTANCE`、など、余分な単語は何ですか。 `_In_` 従来の Windows API では、typedef とプリプロセッサ マクロを広範囲に使用して、呼び出し規約 **、__declspec**宣言、コンパイラ プラグマなど、型やプラットフォーム固有のコードの詳細を抽象化しています。 Visual Studio では、IntelliSense[クイック ヒント](/visualstudio/ide/using-intellisense#quick-info)機能を使用して、これらの型定義とマクロが定義する内容を確認できます。 目的の単語の上にマウスを移動するか、またはそれを選択**し、Ctrl**+**K**を押して Ctrl **Ctrl**+**I**を押すと、定義が含まれている小さなポップアップ ウィンドウが表示されます。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。 多くの場合、パラメーターと戻り値の型では *、SAL 注釈*を使用してプログラミング エラーを検出できます。 詳細については、「 [SAL アノテーションを使用して C/C++ コードの欠陥を減らす](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)」を参照してください。

1. Windows デスクトップ&lt;プログラムには windows.h>が必要です。 &lt;tchar.h>は`TCHAR`、UNICODE シンボルがプロジェクトで定義されている場合に**wchar_t**に最終的に解決されるマクロを定義**します。**  UNICODE を有効にして常にビルドする場合は、TCHAR は必要ありません**wchar_t。**

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain`この機能に加えて、すべての Windows デスクトップ アプリケーションにもウィンドウ プロシージャ関数が必要です。 この関数は通常は`WndProc`という名前ですが、好きな名前を付けることができます。 `WndProc` の構文は、次のとおりです。

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   この関数では、*イベント*が発生したときにアプリケーションが Windows から受信する*メッセージ*を処理するコードを記述します。 たとえば、ユーザーがアプリケーションで [OK] ボタンをクリックすると、Windows からメッセージが送信され、関数内に適切な`WndProc`処理を行うコードを記述できます。 これはイベント*の処理*と呼ばれます。 アプリケーションに関連するイベントのみを処理します。

   詳細については、「 [ウィンドウ プロシージャ](/windows/win32/winmsg/window-procedures)」を参照してください。

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 関数に機能を追加するには

1. 関数では`WinMain`、[型 WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)の構造体を設定します。 構造には、アプリケーションアイコン、ウィンドウの背景色、タイトルバーに表示する名前などのウィンドウに関する情報が含まれています。 重要なのは、ウィンドウ プロシージャへの関数ポインタが含まれています。 一般的な `WNDCLASSEX` 構造体の例を次に示します。

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

   上記の構造体のフィールドについては[、WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)を参照してください。

1. ウィンドウと`WNDCLASSEX`、ウィンドウにメッセージを送信する方法を知ることができるように、Windows に登録します。 [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) 関数を使用して、ウィンドウ クラス構造体を引数として渡します。 マクロ`_T`は、型を使用するため使用`TCHAR`されます。

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

   この関数は、`HWND`ウィンドウへのハンドルである を返します。 ハンドルは、Windows が開いているウィンドウを追跡するために使用するポインターのようなものです。 詳細については、「 [Windows のデータ型](/windows/win32/WinProg/windows-data-types)」を参照してください。

1. この時点でウィンドウは作成されましたが、ウィンドウを表示するように Windows に指示する必要があります。 このコードでは、次の処理が行われます。

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   `WndProc`関数をまだ実装していないため、表示されるウィンドウにはあまりコンテンツがありません。 つまり、アプリケーションは Windows が現在送信しているメッセージをまだ処理していません。

1. メッセージを処理するために、まず Windows が送信するメッセージをリッスンするメッセージ ループを追加します。 アプリケーションがメッセージを受信すると、このループは処理対象の関数に`WndProc`メッセージをディスパッチします。 メッセージ ループのコードは、次のようになります。

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

   処理する重要なメッセージの 1 つは[、WM_PAINT](/windows/win32/gdi/wm-paint)メッセージです。 アプリケーションは、表示される`WM_PAINT`ウィンドウの一部を更新する必要があるときにメッセージを受け取ります。 このイベントは、ユーザーがウィンドウをウィンドウの前に移動し、その後、ウィンドウをもう一度移動したときに発生します。 アプリケーションでは、これらのイベントがいつ発生したかはわかりません。 Windows だけが認識しているので、アプリにメッセージを`WM_PAINT`通知します。 ウィンドウが最初に表示されるとき、すべてのウィンドウを更新する必要があります。

   `WM_PAINT` メッセージを処理するには、まず [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint)を呼び出して、ウィンドウのテキスト、ボタン、その他のコントロールをレイアウトするためのすべてのロジックを処理し、次に [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint)を呼び出します。 アプリケーションの場合、開始呼び出しと終了呼び出しの間のロジックは、文字列 "こんにちは、 Windows デスクトップ! ウィンドウです。 次のコードでは、文字列を表示するために [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) 関数が使用されていることに注意してください。

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

   `HDC`コードでは、デバイス コンテキストへのハンドルは、Windows がアプリケーションがグラフィックス サブシステムと通信できるようにするために使用するデータ構造です。 `BeginPaint`と`EndPaint`関数を使用すると、アプリケーションは良い市民のように動作し、必要以上にデバイス コンテキストを使用しません。 この関数は、グラフィックス サブシステムを他のアプリケーションで使用できるようにするのに役立ちます。

1. 通常、アプリケーションは他の多くのメッセージを処理します。 たとえば、ウィンドウが最初に作成されたとき[WM_CREATE、](/windows/win32/winmsg/wm-create)ウィンドウが閉じられたときに[WM_DESTROY。](/windows/win32/winmsg/wm-destroy) 単純でも完成した `WndProc` 関数のコードを次に示します。

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

約束したように、ここでは、動作するアプリケーションの完全なコードです。

### <a name="to-build-this-example"></a>この例をビルドするには

1. エディタで*HelloWindowsDesktop.cpp*に入力したコードをすべて削除します。 次のコード例をコピーし、*それを HelloWindowsDesktop.cpp*に貼り付けます。

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

1. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 コンパイルの結果は、Visual Studio の **[出力**] ウィンドウに表示されます。

   ![デスクトップ アプリケーション プロジェクトをビルドする](../build/media/desktop-app-project-build-150.gif "デスクトップ アプリケーション プロジェクトをビルドする")

1. アプリケーションを実行するには、**F5** を押します。 "こんにちは、 Windows デスクトップ" というテキストを含むウィンドウ 画面の左上隅に表示されます。

   ![デスクトップ アプリケーション プロジェクトの実行](../build/media/desktop-app-project-run-157.PNG "デスクトップ アプリケーション プロジェクトの実行")

おめでとうございます! このチュートリアルを完了し、従来の Windows デスクトップ アプリケーションを構築しました。

## <a name="see-also"></a>関連項目

[デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)
