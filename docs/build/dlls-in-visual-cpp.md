---
title: Visual Studio でC++の C/dll の作成
ms.date: 07/18/2019
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
ms.openlocfilehash: 33f002143e306c99b4d17b7a01ddd4a9738e38e7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493280"
---
# <a name="create-cc-dlls-in-visual-studio"></a>Visual Studio でC++の C/dll の作成

Windows では、ダイナミックリンクライブラリ (DLL) は、関数とリソースの共有ライブラリとして機能する実行可能ファイルの一種です。 動的リンクは、実行可能ファイルが関数を呼び出したり、別のファイルに格納されているリソースを使用したりできるようにするオペレーティングシステムの機能です。 これらの関数とリソースはコンパイルできるだけでなく、これらを使用する実行可能ファイルとは別に配置することができます。 DLL はスタンドアロンの実行可能ファイルではありません。これは、それを呼び出すアプリケーションのコンテキストで実行されます。 オペレーティングシステムは、アプリケーションが読み込まれるとき (*暗黙のリンク*)、または実行時にオンデマンドで (*明示的なリンク*)、DLL をアプリケーションのメモリ領域に読み込むことができます。 また、DLL は、実行可能ファイル間で関数とリソースを共有しやすくします。 メモリ内の DLL の内容には、同時に複数のアプリケーションがアクセスできます。

## <a name="differences-between-dynamic-linking-and-static-linking"></a>動的リンクと静的リンクの違い

静的リンクでは、スタティックライブラリ内のすべてのオブジェクトコードが、ビルド時にそれを使用する実行可能ファイルにコピーされます。 動的リンクには、実行時に Windows によって必要な情報のみが含まれ、データ項目または関数を含む DLL を検索して読み込むことができます。 DLL を作成するときに、この情報を含むインポートライブラリも作成します。 DLL を呼び出す実行可能ファイルをビルドすると、リンカーは、インポートライブラリ内のエクスポートされたシンボルを使用して、Windows ローダーのこの情報を格納します。 ローダーが DLL を読み込むと、DLL がアプリケーションのメモリ空間にマップされます。 存在する場合は、dll 内`DllMain`の特別な関数が呼び出され、dll に必要な初期化を実行します。

<a name="differences-between-applications-and-dlls"></a>

## <a name="differences-between-applications-and-dlls"></a>アプリケーションと Dll の違い

Dll とアプリケーションはどちらも実行可能モジュールですが、いくつかの点で異なります。 エンドユーザーにとって最も顕著な違いは、Dll は直接実行できるアプリケーションではないということです。 システム側から見ると、アプリケーションと DLL には次の 2 つの根本的な違いがあります。

- アプリケーションはシステム内で稼働する複数のインスタンスを同時に持つことができるのに対し、DLL のインスタンスは 1 つしかありません。

- アプリケーションは、スタック、実行スレッド、グローバルメモリ、ファイルハンドル、およびメッセージキューなどを所有できるプロセスとして読み込むことができますが、DLL を使用することはできません。

<a name="advantages-of-using-dlls"></a>

## <a name="advantages-of-using-dlls"></a>Dll を使用する利点

コードとリソースへの動的リンクには、静的リンクよりもいくつかの利点があります。

- 動的リンクはメモリを節約し、スワップを減らします。 多くのプロセスでは、DLL を同時に使用して、メモリ内の DLL の読み取り専用部分の1つのコピーを共有できます。 これに対し、静的にリンクされたライブラリを使用してビルドされるすべてのアプリケーションには、Windows がメモリに読み込む必要があるライブラリコードの完全なコピーがあります。

- ダイナミックリンクを使用すると、ディスク領域と帯域幅が節約されます。 複数のアプリケーションが、ディスク上の DLL を共有できます。 これに対して、スタティックリンクライブラリを使用してビルドされた各アプリケーションは、実行可能イメージにリンクされたライブラリコードを持っています。これにより、より多くのディスク領域が使用され、転送に必要な帯域幅が増えます。

- メンテナンス、セキュリティの修正、およびアップグレードが簡単になります。 アプリケーションが DLL で共通の関数を使用する場合、関数の引数と戻り値が変わらない限り、バグの修正を実装し、DLL に更新を配置することができます。 Dll が更新されると、それらを使用するアプリケーションを再コンパイルまたは再リンクする必要がなくなり、デプロイされるとすぐに新しい DLL が使用されます。 これに対して、静的にリンクされたオブジェクトコードを修正する場合は、それを使用するすべてのアプリケーションの再リンクと再配置が必要になります。

- Dll を使用して、市場でのサポートを提供できます。 たとえば、アプリケーションの出荷時には利用できなかったディスプレイをサポートするよう、ディスプレイ ドライバー DLL を後から変更することもできます。

- 明示的リンクを使用して、実行時に DLL を検出して読み込むことができます。たとえば、アプリケーションの拡張機能を再構築または再デプロイすることなく、アプリに新しい機能を追加します。

- 動的リンクを使用すると、さまざまなプログラミング言語で記述されたアプリケーションのサポートが容易になります。 異なるプログラミング言語で書かれたプログラムでも、関数の呼び出し規則に従う限り、同じ DLL 関数を呼び出すことができます。 ただし、引数がスタックにプッシュされる順序、スタックのクリアをアプリケーションと関数のどちらが行うか、引数のレジスタ渡しの有無に関しては、使用する側のプログラムと DLL 関数の間に互換性が成立している必要があります。

- 動的リンクは、MFC ライブラリクラスを拡張するための機構を提供します。 既存の MFC クラスの派生クラスを作成し、MFC アプリケーションから使用可能な MFC 拡張 DLL に配置できます。

- 動的リンクを使用すると、アプリケーションの国際対応バージョンを簡単に作成できます。 Dll は、ロケール固有のリソースを提供するのに便利な方法です。これにより、アプリケーションの国際対応バージョンを簡単に作成できます。 アプリケーションの多くのローカライズされたバージョンを配布するのではなく、各言語の文字列とイメージを別のリソース DLL に配置することができます。その後、アプリケーションは実行時にそのロケールに対応するリソースを読み込むことができます。

Dll を使用する場合の潜在的な欠点は、アプリケーションが自己完結していないことです。これは、個別の DLL モジュールが存在するかどうかによって異なります。これは、インストールの一部として展開または検証する必要があります。

## <a name="more-information-on-how-to-create-and-use-dlls"></a>Dll を作成して使用する方法の詳細については、こちらを参照してください。

次のトピックでは、Visual Studio で C/C++ dll を作成する方法の詳細について説明します。

[チュートリアル: ダイナミック リンク ライブラリの作成と使用 (C++)](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)<br/>
Visual Studio を使用して DLL を作成および使用する方法について説明します。

[DLL の種類](kinds-of-dlls.md)<br/>
ビルドできる各種 DLL に関する情報を提供します。

[DLL に関してよく寄せられる質問](dll-frequently-asked-questions.md)<br/>
DLL に関してよく寄せられる質問への回答を示します。

[実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md)<br/>
DLL との明示的なリンクと暗黙的なリンクについて説明します。

[DLL の初期化](run-time-library-behavior.md#initializing-a-dll)<br/>
Dll の読み込み時に実行する必要がある DLL 初期化コードについて説明します。

[DLL と Visual C++ ランタイム ライブラリの動作](run-time-library-behavior.md)<br/>
ランタイム ライブラリで DLL の起動処理をどのように実行するかについて説明します。

[LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)<br/>
**LoadLibrary**の使用方法`AfxLoadLibrary`と、実行時に DLL に明示的にリンクする方法について説明します。

[GetProcAddress](getprocaddress.md)<br/>
**GetProcAddress**を使用して DLL 内のエクスポート関数のアドレスを取得する方法について説明します。

[FreeLibrary と AfxFreeLibrary](freelibrary-and-afxfreelibrary.md)<br/>
**FreeLibrary**の使用方法`AfxFreeLibrary`と、DLL モジュールが不要になった場合について説明します。

[ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)<br/>
Windows オペレーティング システムがシステム上の DLL を検索するために使用する検索パスについて説明します。

[MFC と動的にリンクされるレギュラー MFC DLL のモジュール状態](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)<br/>
MFC に動的にリンクされるレギュラー MFC DLL のモジュールの状態について説明します。

[MFC 拡張 DLL](extension-dlls-overview.md)<br/>
既存の MFC ライブラリ クラスから派生した再利用可能なクラスを主に実装する DLL について説明します。

[リソースのみの DLL の作成](creating-a-resource-only-dll.md)<br/>
アイコン、ビットマップ、文字列、ダイアログ ボックスなどのリソースだけを含む、リソースのみの DLL について説明します。

[MFC アプリケーションのローカライズされたリソース:サテライト DLL](localized-resources-in-mfc-applications-satellite-dlls.md)<br/>
混合言語にローカライズされるアプリケーションの作成に役立つ、サテライト DLL のサポートを強化します。

[インポートとエクスポート](importing-and-exporting.md)<br/>
アプリケーションへのパブリック シンボルのインポート、または DLL からの関数のエクスポートについて説明します。

[Active テクノロジと DLL](active-technology-and-dlls.md)<br/>
オブジェクト サーバーを DLL 内部に実装できます。

[DLL でのオートメーション](automation-in-a-dll.md)<br/>
MFC DLL ウィザードの [オートメーション] オプションについて説明します。

[MFC DLL の名前付け規則](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)<br/>
MFC に含まれる DLL やライブラリに適用される一定の名前付け規則について説明します。

[Visual Basic アプリケーションからの DLL 関数の呼び出し](calling-dll-functions-from-visual-basic-applications.md)<br/>
Visual Basic アプリケーションから DLL 関数を呼び出す方法について説明します。

## <a name="related-sections"></a>関連項目

[DLL の一部としての MFC の使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)<br/>
MFC ライブラリを Windows ダイナミックリンクライブラリの一部として使用できるようにするレギュラー MFC Dll について説明します。

[MFC の DLL バージョン](../mfc/tn033-dll-version-of-mfc.md)<br/>
Mfcxx.dll と MFCxxD .dll を使用する方法について説明します。ここで、x は MFC バージョン番号であり、mfc アプリケーションと MFC 拡張 Dll との共有ダイナミックリンクライブラリです。
