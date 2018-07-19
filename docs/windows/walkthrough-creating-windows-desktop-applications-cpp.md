---
title: 'チュートリアル: 作成、従来の Windows デスクトップ アプリケーション (C++) |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 1/11/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e5581292ec163a2e745802c66a87c14a8457f141
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>チュートリアル: 作成、従来の Windows デスクトップ アプリケーション (C++)

このチュートリアルでは、Visual Studio での従来 Windows デスクトップ アプリケーションを作成する方法を示します。 作成するアプリケーションの例では、Windows API を使用して、「こんにちは, Windows デスクトップ!」を表示 。ウィンドウです。 このチュートリアルで開発したコードは、他の Windows デスクトップ アプリケーションを作成するためのパターンとして使用できます。

Windows API (とも呼ばれる、Win32 API、Windows デスクトップの API、および Windows クラシック API) とは、Windows アプリケーションを作成するための C 言語ベース フレームワークです。 1980 年代以降の存在にした場合と、数十年の Windows アプリケーションの作成に使用されています。 この API は、MFC、ATL、および .NET framework などの上に構築された高度なとプログラムを簡単にフレームワークです。 UWP アプリとストア アプリの C で記述されたコードを最も最近 + WinRT の下にこの API を使用します。 Windows API の詳細については、次を参照してください。 [Windows API インデックス](https://msdn.microsoft.com/library/windows/desktop/ff818516.aspx)です。 Windows アプリケーションを作成する方法はたくさんありますが、これが最初。

> [!IMPORTANT]
> ここでは簡略化のため、一部のコード ステートメントはテキストで除外されます。 [コードをビルド](#build-the-code)このドキュメントの最後のセクションでは、完全なコードを示しています。

## <a name="prerequisites"></a>必須コンポーネント

- Microsoft Windows 7 またはそれ以降のバージョンを実行するコンピューター。 Windows 10 は、最適な開発エクスペリエンスをお勧めします。

- Visual Studio 2017 のコピー。 ダウンロードして Visual Studio をインストールする方法については、次を参照してください。 [Visual Studio のインストール 2017](/visualstudio/install/install-visual-studio)です。 インストーラーを実行するときに、以下のことを確認、 **C++ を使用したデスクトップ開発**ワークロードがオンになっています。 Visual Studio をインストールしたときにこのワークロードをインストールしなかった場合、心配しないでください。 インストーラーをもう一度実行して、今すぐインストールします。

   ![C++ を使用したデスクトップ開発](../build/media/desktop-development-with-cpp.png "C++ を使用したデスクトップの開発")

- Visual Studio IDE の基本的な使い方を理解します。 前に、の Windows デスクトップ アプリを使用している場合保持できます可能性があります。 概要については、次を参照してください。 [Visual Studio IDE 機能のツアー](/visualstudio/ide/visual-studio-ide)です。

- 進めるために、C++ 言語の基本の十分な理解します。 心配しないで、あまり複雑な何もしません。

## <a name="create-a-windows-desktop-project"></a>Windows デスクトップ プロジェクトを作成します。

次の手順を最初の Windows デスクトップ プロジェクトを作成し、作業中の Windows デスクトップ アプリケーションのコードを入力します。 Visual Studio 2017 15.3 のバージョンより古い Visual Studio のバージョンを使用している場合に進みます[を Visual Studio 2017 RTM では、Windows のデスクトップ プロジェクトを作成する](#create-in-vs2017-rtm)です。

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Visual Studio 2017 更新 15.3 以降の Windows デスクトップ プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、**[プロジェクト]** を選択します。

1. **新しいプロジェクト**ダイアログ ボックスで、左側のウィンドウで展開**インストール**、 **Visual C**選択してから、 **Windows デスクトップ**です。 中央のペインで選択**Windows デスクトップ ウィザード**です。

   **名前**ボックスに、たとえば、プロジェクトの名前を入力*DesktopApp*です。 **[OK]** をクリックします。

   ![DesktopApp プロジェクト](../build/media/desktop-app-new-project-name-153.png "DesktopApp プロジェクトの名前")

1. **Windows デスクトップ プロジェクト**] ダイアログで、**アプリケーションの種類**[ **Windows アプリケーション (.exe)** です。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 選択**OK**プロジェクトを作成します。

   ![Windows デスクトップ プロジェクト ウィザードで DesktopApp を作成](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp を Windows デスクトップ プロジェクト ウィザードで作成します。")

1. **ソリューション エクスプ ローラー**を右クリックし、 **DesktopApp**プロジェクト**追加**を選択し**新しい項目の**します。

   ![DesktopApp プロジェクトへ新しい項目の追加](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp プロジェクトへ新しい項目の追加")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 **名前**ボックスに、たとえば、ファイルの名前を入力*HelloWindowsDesktop.cpp*です。 **[追加]** をクリックします。

   ![DesktopApp プロジェクトに追加の .cpp ファイル](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp プロジェクトへの .cpp ファイルの追加")

プロジェクトを作成するようになりましたし、ソース ファイルがエディターで開いています。 続行するにはへ進んで[コード作成](#create-the-code)です。

### <a id="create-in-vs2017-rtm"></a> Visual Studio 2017 RTM では、Windows のデスクトップ プロジェクトを作成するには

1. **[ファイル]** メニューの **[新規作成]** を選択し、**[プロジェクト]** を選択します。

1. **新しいプロジェクト**ダイアログ ボックスで、左側のウィンドウで展開**インストール**、**テンプレート**、 **Visual C**、し、 **Win32**です。 中央のペインで、 **[Win32 プロジェクト]** を選択します。

   **名前**ボックスに、たとえば、プロジェクトの名前を入力*DesktopApp*です。 **[OK]** をクリックします。

   ![DesktopApp プロジェクト](../build/media/desktop-app-new-project-name-150.png "DesktopApp プロジェクトの名前")

1. **概要**のページ、 **Win32 アプリケーション ウィザード**を選択**次**です。

   ![Win32 アプリケーション ウィザード の概要作成 DesktopApp](../build/media/desktop-app-win32-wizard-overview-150.png "DesktopApp を Win32 アプリケーション ウィザード の概要の作成")

1. **アプリケーション設定** ページの **アプリケーションの種類** **Windows アプリケーション**です。 **[追加のオプション]** の **[空のプロジェクト]** を選択します。 選択**完了**プロジェクトを作成します。

   ![Win32 アプリケーション ウィザードの設定で DesktopApp を作成する](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp の Win32 アプリケーション ウィザードの設定の作成")

1. **ソリューション エクスプ ローラー**DesktopApp プロジェクトを右クリックしてで、**追加**を選択し**新しい項目の**します。

   ![DesktopApp プロジェクトへ新しい項目の追加](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp プロジェクトへ新しい項目の追加")

1. **[新しい項目の追加]** ダイアログ ボックスで、 **[C++ ファイル (.cpp)]** をクリックします。 **名前**ボックスに、たとえば、ファイルの名前を入力*HelloWindowsDesktop.cpp*です。 **[追加]** をクリックします。

   ![DesktopApp プロジェクトに追加の .cpp ファイル](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp プロジェクトへの .cpp ファイルの追加")

プロジェクトを作成するようになりましたし、ソース ファイルがエディターで開いています。

## <a name="create-the-code"></a>コードを作成します。

次に、Visual Studio での Windows デスクトップ アプリケーションのコードを作成する方法を学習します。

### <a name="to-start-a-windows-desktop-application"></a>Windows デスクトップ アプリケーションを開始するには

1. すべての c アプリケーションおよび C++ アプリケーションが必要な`main`関数のすべての Windows デスクトップ アプリケーションが必要、開始点として、`WinMain`関数。 `WinMain` の構文は、次のとおりです。

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   この関数の戻り値とパラメーターについては、次を参照してください。 [WinMain エントリ ポイント](https://msdn.microsoft.com/library/windows/desktop/ms633559)です。

   > [!NOTE]
   > どのようななどは、そのすべての余分な単語**コールバック**、または**HINSTANCE**、または**\_で\_** しますか? 従来の Windows API が typedef を使用し、プリプロセッサ マクロを抽象化して広範な型およびプラットフォーム固有の詳細情報の一部のコード、呼び出し規約など **_ _declspec**宣言、およびコンパイラ プラグマ。 Visual Studio での IntelliSense を使用することができます[クイック ヒント](/visualstudio/ide/using-intellisense#quick-info)これら typedef とマクロをどのような定義を表示する機能。 、目的の単語の上にマウスを置くか、選択して ctrl キーを押し K、ctrl キーを押す--i は定義を格納する小さなポップアップ ウィンドウです。 詳細については、「[IntelliSense の使用](/visualstudio/ide/using-intellisense)」を参照してください。 パラメーターと戻り値の型が多くの場合、使用して*SAL 注釈*に役立つプログラミング エラーをキャッチします。 詳細については、次を参照してください。 [c/c++ コードの不具合の削減に SAL 注釈を使用して](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)です。

1. Windows デスクトップ プログラムを必要と&lt;windows.h >。 &lt;tchar.h > を定義、`TCHAR`最終的に解決するには、マクロに`wchar_t`UNICODE シンボルが、プロジェクトで定義されている場合は、それ以外の場合に解決される`char`です。  常に有効になっている unicode をビルドする場合、TCHAR 必要はありませんし、wchar_t を直接使用できます。

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain` 関数のほかに、すべての Windows デスクトップ アプリケーションにはウィンドウ プロシージャ関数が必要です。 この関数の名前は通常`WndProc`できる名前を付けるお好きなようですが。 `WndProc` の構文は、次のとおりです。

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   この関数で処理するコードを記述する*メッセージ*Windows からアプリケーションを受信するときに*イベント*発生します。 たとえば、ユーザーが [ok] ボタンを選択したアプリケーションで場合、Windows するメッセージが送信され、内のコードを記述することができます、`WndProc`はどのような作業が適切な関数をします。 これと呼ばれる*処理*イベント。 アプリケーションに関連するイベントを処理するだけです。

   詳細については、次を参照してください。[ウィンドウ プロシージャ](https://msdn.microsoft.com/library/windows/desktop/ms632593)です。

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 関数に機能を追加するには

1. `WinMain`関数、型の構造を設定する[WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577)です。 この構造体には、たとえば、アプリケーションのアイコン、ウィンドウのタイトル バーに、非常に重要なは、ウィンドウ プロシージャに関数ポインターを表示する名前の背景色は、ウィンドウに関する情報が含まれています。 一般的な `WNDCLASSEX` 構造体の例を次に示します。

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

   この構造体のフィールドの詳細については、次を参照してください。 [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577)です。

1. 登録する必要があります、 `WNDCLASSEX` windows メッセージを送信する方法と、ウィンドウに関することができるようにします。 使用して、 [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587)関数を引数として、ウィンドウ クラス構造体を渡します。 `_T`マクロを使用して使用するため、`TCHAR`型です。

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

1. これで、ウィンドウを作成できます。 使用して、 [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679)関数。

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

   この関数を返します、 `HWND`、これは、ウィンドウのハンドル。 ハンドルは、Windows が開いているウィンドウの追跡に使用するポインターのようなものです。 詳細については、次を参照してください。 [Windows Data Types](https://msdn.microsoft.com/library/windows/desktop/aa383751)です。

1. この時点で、ウィンドウが作成されましたが、表示するのには Windows に通知する必要があります。 このコードが何を行っています。

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   まだを実装していないため、表示されたウィンドウは多くのコンテンツを持ちません、`WndProc`関数。 つまり、アプリケーション処理されていませんまだメッセージを Windows に送信するようになりました。

1. メッセージを処理するために最初に Windows を送信するメッセージをリッスンするようにメッセージ ループを追加します。 このループをディスパッチするアプリケーションでは、メッセージを受信したときに、`WndProc`処理する関数。 メッセージ ループのコードは、次のようになります。

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   構造体とメッセージ ループ内の関数の詳細については、次を参照してください[MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958)、 [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936)、 [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955)、および[DispatchMessage](https://msdn.microsoft.com/library/windows/desktop/ms644934)。

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

   1 つの重要なメッセージを処理するは、 [WM_PAINT](https://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージ。 アプリケーションは、表示しているウィンドウの一部の更新が必要になったときにこのメッセージを受け取ります このイベントは、ユーザーは、ウィンドウの前にウィンドウを移動し、移動、休暇からもう一度ときに発生します。 次のようにイベントが発生したときに、アプリケーションを認識しませんユーザーに通知するため、Windows のみを知っている`WM_PAINT`です。 ウィンドウが最初に表示される場合すべての更新する必要があります。

   処理するために、`WM_PAINT`メッセージ、最初の呼び出し[BeginPaint](https://msdn.microsoft.com/library/windows/desktop/dd183362)、テキスト、ボタン、およびウィンドウで、その他のコントロールをレイアウトするすべてのロジックを処理し、呼び出す[EndPaint](https://msdn.microsoft.com/library/windows/desktop/dd162598)です。 このアプリケーションで、最初の呼び出しと最後の呼び出しの間のロジックは、文字列「こんにちは, Windows デスクトップ!」を表示するには ウィンドウです。 次のコードでわかるように、 [TextOut](https://msdn.microsoft.com/library/windows/desktop/dd145133)関数は、文字列の表示に使用します。

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

   `HDC` このコードでは、グラフィックス サブシステムと通信するアプリケーションを有効にするために使用されるデータ構造体であるデバイス コンテキストへのハンドルです。 `BeginPaint`と`EndPaint`関数では、アプリケーションが良き市民ように動作し、必要以上に長くなりますデバイス コンテキストを使用しないことを確認してください。 これにより、グラフィックス サブシステムが他のアプリケーションで使用できることを確認します。

1. アプリケーションで他の多くのメッセージをたとえば、処理通常[WM_CREATE](https://msdn.microsoft.com/library/windows/desktop/ms632619)ウィンドウが作成されると、および[WM_DESTROY](https://msdn.microsoft.com/library/windows/desktop/ms632620)ウィンドウが閉じているときにします。 単純でも完成した `WndProc` 関数のコードを次に示します。

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

## <a name="build-the-code"></a>コードをビルドします。

、約束どおりに動作するアプリケーションの完全なコードを次に示します。

### <a name="to-build-this-example"></a>この例をビルドするには

1. エディターで HelloWindowsDesktop.cpp に入力したすべてのコードを削除します。 このコード例をコピーし、HelloWindowsDesktop.cpp に貼り付けます。

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
      _In_ HINSTANCE hPrevInstance,
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

1. **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。 コンパイルの結果が表示されます、**出力**Visual Studio のウィンドウ。

   ![プロジェクトをビルドします DesktopApp](../build/media/desktop-app-project-build-150.gif "DesktopApp プロジェクトのビルド")

1. 実行するには、アプリケーション キーを押して**f5 キーを押して**です。 テキスト「こんにちは, Windows デスクトップ!」を含むウィンドウ 画面の左上隅に表示されます。

   ![DesktopApp プロジェクトを実行](../build/media/desktop-app-project-run-150.gif "DesktopApp プロジェクトを実行")

おめでとうございます!  このチュートリアルを完了して、従来 Windows デスクトップ アプリケーションを構築することがあります。

## <a name="see-also"></a>関連項目

[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)
