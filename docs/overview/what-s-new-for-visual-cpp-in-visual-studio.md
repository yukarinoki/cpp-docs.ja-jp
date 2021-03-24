---
title: Visual Studio での C++ の新機能
description: Visual Studio 2019 での Microsoft C/C++ コンパイラとツールにおける新機能と修正プログラム。
ms.date: 03/03/2021
ms.technology: cpp-ide
ms.openlocfilehash: c48b733ad18d57917220b443bd18830441dc693c
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "103087182"
---
# <a name="whats-new-for-c-in-visual-studio"></a>Visual Studio での C++ の新機能

Visual Studio 2019 には、Microsoft C++ 環境に対する多くの更新プログラムと修正プログラムが導入されています。 コンパイラおよびツールの多くのバグと問題を修正しました。 多くの問題は、 **[フィードバックの送信]** の [[問題の報告]](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019&preserve-view=true) および [[提案の送信]](https://aka.ms/feedback/suggest?space=62) オプションを通じてお客様から寄せられたものです。 バグ レポートをお寄せいただきありがとうございました。

Visual Studio 全体の新機能の詳細については、「[Visual Studio 2019 の新機能](/visualstudio/ide/whats-new-visual-studio-2019)」を参照してください。 Visual Studio 2017 での C++ の新機能については、「[Visual Studio 2017 での C++ の新機能](what-s-new-for-cpp-2017.md)」を参照してください。 Visual Studio 2015 以前のバージョンでの C++ の新機能については、「[Visual Studio 2003 から 2015 の Visual C++ の新機能](../porting/visual-cpp-what-s-new-2003-through-2015.md)」を参照してください。 C++ ドキュメントの新着記事については、[Microsoft C++ ドキュメントの新着記事](whats-new-cpp-docs.md)に関するページを参照してください。

## <a name="whats-new-for-c-in-visual-studio-version-169"></a>Visual Studio バージョン 16.9 での C++ の新機能

Visual Studio バージョン 16.9 での新機能とバグ修正の概要については、「[Visual Studio 2019 バージョン 16.9 の新機能](/visualstudio/releases/2019/release-notes#--visual-studio-2019-version-1690-)」を参照してください。

- [Address Sanitizer](../sanitizers/asan.md):

  - Windows での Address Sanitizer のサポートが試験段階ではなくなり、一般提供が開始されました。

  - `RtlAllocateHeap` のサポートが拡張され、実行可能なメモリ プールを作成する際の `RtlCreateHeap` および `RtlAllocateHeap` インターセプターに関する互換性の問題が修正されました。

  - 従来の `GlobalAlloc` および `LocalAlloc` ファミリのメモリ関数に対するサポートが追加されました。 これらのインターセプターは、環境フラグ `ASAN_OPTIONS=windows_hook_legacy_allocators=true` を設定することによって有効にすることができます。

  - シャドウ メモリ インターリーブおよびインターセプト エラーに関するエラー メッセージが更新され、問題と解決策が明確になりました。

  - IDE の統合により、ASan で報告できる例外の完全なコレクションを処理できるようになりました。

  - コンパイラとリンカーにより、ASan を使用してビルドしているがデバッグ情報を出力していないことが検出された場合に、デバッグ情報を出力することが提案されます。

- 新しい CL スイッチ **`/openmp:llvm`** を使用して、LLVM バージョンの OpenMP ランタイムをターゲットにすることができるようになりました。 これにより、`#pragma omp` セクションでの `lastprivate` 句と、並列 `for` ループでの符号なしインデックス変数に対するサポートが追加されます。 現在、 **`/openmp:llvm`** スイッチは amd64 ターゲットでのみ使用可能であり、まだ試験段階です。

- Visual Studio CMake プロジェクトで、リモート Windows 開発が高度にサポートされるようになりました。 これには、Windows ARM64 をターゲットとする CMake プロジェクトの構成、リモート Windows コンピューターへのプロジェクトの配置、および Visual Studio からのリモート Windows コンピューター上でのプロジェクトのデバッグが含まれます。

- Windows の Visual Studio に付属する Ninja のバージョンは、バージョン 1.10 に更新されました。 含まれる内容の詳細については、[Ninja 1.10 のリリース ノート](https://groups.google.com/g/ninja-build/c/piOltAhywFA/m/zPfkrTtRCwAJ?pli=1)を参照してください。

- Visual Studio に付属する CMake のバージョンは、バージョン 3.19 に更新されました。 含まれる内容の詳細については、「[CMake 3.19 のリリース ノート](https://cmake.org/cmake/help/latest/release/3.19.html)」を参照してください。

- [STL の多くの lock/guard 型が `nodiscard` としてマークされました](https://github.com/microsoft/STL/pull/1495)。

- IntelliSense:

  - IntelliSense でインポートされたモジュールとヘッダー ユニットの入力候補を提供する安定性と機能性が向上しました。

  - モジュールのインポートでの [定義へ移動]、`export {...}` のインデックス作成のサポート、および同じ名前のモジュールに対するより正確なモジュール参照が追加されました。

  - [参照の直接初期化でのテンポラリのコピー初期化](https://wg21.link/P1358R0)、`__builtin_memcpy` と `__builtin_memmove`、[`constexpr` 関数と `consteval` 関数間の不整合の修正](https://wg21.link/P1937R2)、[定数式での有効期間が延長されたテンポラリ](https://wg21.link/P1968R0)、および[類似した型と参照のバインディング](https://wg21.link/P1358R0)のサポートが追加されたことにより、C++ IntelliSense の言語コンプライアンスが改善されました。

  - make_unique、make_shared、emplace、および emplace_back の入力候補が追加されました。これにより、指定された型パラメーターに基づく入力候補が提供されます。

- MSVC で、お使いのバイナリに必要な正しい Address Sanitizer ランタイムが判断できるようになりました。 この新しい変更は、お使いの Visual Studio プロジェクトで自動的に取得されます。 コマンド ラインで Address Sanitizer を使用する場合は、コンパイラに [`/fsanitize=address`](../build/reference/fsanitize.md) のみを渡せばよくなりました。

- Visual Studio の接続マネージャーで、ECDSA 公開キー アルゴリズムを使用する秘密キーがサポートされるようになりました。

- インストーラーに付属している LLVM と Clang のバージョンが v11 に更新されました。 詳細については、[LLVM](https://releases.llvm.org/11.0.0/docs/ReleaseNotes.html) と [Clang](https://releases.llvm.org/11.0.0/tools/clang/docs/ReleaseNotes.html) のリリース ノートを参照してください。

- Visual Studio で IntelliSense の構成に、ツールチェーン ファイルの CMake 変数が使用されるようになりました。 これにより、Embedded および Android 開発のエクスペリエンスが向上します。

- [より多くの constexpr コンテナー提案](https://wg21.link/P0784R7)を実装することで、デストラクターと新しい式を **`constexpr`** にすることができます。 これにより、 **`constexpr`** `std::vector` や `std::string` などのユーティリティへの道が開かれます。

- C++20 モジュール IntelliSense の延長サポート ([定義に移動]、[モジュールに移動]、[member completion]\(メンバー完了\) など)。

- [省略形の関数テンプレート](https://en.cppreference.com/w/cpp/language/function_template#Abbreviated_function_template)が MSVC コンパイラーでサポートされるようになりました。

## <a name="whats-new-for-c-in-visual-studio-version-168"></a>Visual Studio バージョン 16.8 での C++ の新機能

Visual Studio バージョン 16.8 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.8 の新機能](/visualstudio/releases/2019/release-notes-v16.8)に関する記事を参照してください。

- C++20 コルーチンが、[`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) および \<coroutine> ヘッダーでサポートされるようになりました。

- IntelliSense で、C++ 20 の \<concepts> と \<ranges> ヘッダー、および概念の定義の名前変更と参照がサポートされるようになりました。

- STL で、C++20 Ranges の多くがサポートされるようになりました。

- [条件付きで自明な特殊メンバー関数](https://wg21.link/P0848R3)が MSVC でサポートされるようになりました。

- C11 と C17 が [`/std:c11` および `/std:c17`](../build/reference/std-specify-language-standard-version.md) スイッチでサポートされるようになりました。

- 追加された STL の機能強化には、[`std::atomic_ref`](https://wg21.link/p0019r8)、[`std::midpoint` と `std::lerp`](https://wg21.link/p0811r3)、および [`std::execution::unseq`](https://wg21.link/p1001r2) の完全なサポートや、[`std::reverse_copy`](../standard-library/algorithm-functions.md#reverse_copy) の最適化などが含まれます。

- Visual Studio に付属している CMake のバージョンを [CMake 3.18](https://cmake.org/cmake/help/latest/release/3.18.html) にアップグレードしました。

- コード分析ツールで、業界標準の静的な分析ログ形式である SARIF 2.1 標準がサポートされるようになりました。

- Linux プロジェクトで見つからないビルド ツールがある場合、ツール バーには警告が表示され、エラー一覧には不足しているツールが明記されるようになりました。

- Linux コア ダンプを、リモートの Linux システムまたは WSL の Visual Studio から直接デバッグできるようになりました。

- C++ Doxygen でのコメントの生成用に、新しいコメント スタイル オプションが追加されました (`/*!` と `//!`)。

- 追加の [vcpkg の発表](https://aka.ms/vcpkg/team)。

- 未評価のコンテキストでのラムダのコンパイラ サポート。

- マルチスレッドでの PDB の作成により、[`/DEBUG:FULL`](../build/reference/debug-generate-debug-info.md) リンクのパフォーマンスが向上しました。 いくつかの大規模なアプリケーションと AAA ゲームでは、リンクの速度が 2 から 4 倍高速になっています。

- Visual Studio デバッガーで **`char8_t`** がサポートされるようになりました。

- clang-cl を使用した ARM64 プロジェクトのサポート。

- [Intel AMX 組み込み](https://software.intel.com/content/www/us/en/develop/documentation/cpp-compiler-developer-guide-and-reference/top/compiler-reference/intrinsics/intrinsics-for-intel-advanced-matrix-extensions-intel-amx-instructions.html)サポート。

## <a name="whats-new-for-c-in-visual-studio-version-167"></a>Visual Studio バージョン 16.7 での C++ の新機能

Visual Studio バージョン 16.7 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.7 の新機能](/visualstudio/releases/2019/release-notes-v16.7)に関する記事を参照してください。

- Microsoft はリモート C++ について、sh、csh、bash、tsch、ksh、zsh、dash など、幅広い Linux のディストリビューションとシェルをサポートするようになりました。 ConnectionManager.exe を利用して新しい "shell" プロパティを変更することでリモート接続のシェル選択をオーバーライドできます。 このサポートは、リモート Linux システムまたは WSL をターゲットにする MSBuild ベースの Linux プロジェクトと CMake プロジェクトの両方でテストされています。

- Ninja (インクリメンタル ビルドを非常に短時間で評価するビルド システム) を使用し、MSBuild ベースの Linux プロジェクトのインクリメンタル ビルド時間を改善できるようになりました。 [全般プロパティ] ページで [インクリメンタル ビルドを有効にする] を [With Ninja]\(Ninja を使用する\) に設定することでこの機能を選択できます。 Ninja (ninja-build) はリモートの Linux システムまたは WSL にインストールする必要があります。

- 新しい C++20 標準ライブラリ機能が実装されました。 詳細な一覧については、[GitHub の STL Changelog](https://github.com/microsoft/STL/wiki/Changelog) を参照してください。

- [接続マネージャー](../linux/connect-to-your-remote-linux-computer.md#set-up-the-remote-connection)で、既定のリモート SSH 接続を編集および設定できるようになりました。 つまり、既存のリモート接続を編集したり (IP アドレスが変更された場合など)、既定の接続を CMakeSettings.json や launch.vs.json 内で使用されるように設定したりすることができます。 リモート SSH 接続を使用すると、リモートの Linux システム上でのプロジェクトのビルドおよびデバッグを、Visual Studio から直接行うことができます。

- Visual Studio で、Windows 上の Clang (clang-cl) に対する IntelliSense サポートが強化されました。 clang インクルード パスに clang ライブラリが含まれるようになりました。std ライブラリを使用する際のエディター内の波線表示を改善しました。clang モードに C++2a のサポートを追加しました。

- C++ プロジェクトで、コード エラーに下線を引いてみると、提案されるより多くのクイック修正を参照できるようになりました。 **[ツール] > [オプション] > [テキスト エディター] > [C/C++] > [試験的]** でこの機能を有効にします。 **[実験的なコード リンターの無効化]** を false に設定します。 詳細については、[C++ チーム ブログ](https://aka.ms/cpp/isensecodelinter)を参照してください。

- 追加の安全機能を C++ に組み込むための新しいコード分析規則を 4 つ追加しました: [C26817](../code-quality/c26817.md)、[C26818](../code-quality/c26818.md)、[C26819](../code-quality/c26819.md)、[C26820](../code-quality/c26820.md)。

- gdbserver を使用してリモート システム上で CMake プロジェクトをデバッグするための最上級のサポートが追加されました。

- Visual Studio での C++ 用の AddressSanitizer の試験的な実装により、メモリ破損エラーを簡単に見つけることができるようになりました。現在、x64 ネイティブ プロジェクトで利用できます。 デバッグ ランタイム ( **`/MTd`** 、 **`/MDd`** 、 **`/LDd`** ) の使用もサポートされるようになりました。

- IntelliSense で、概念、指定された初期化子などの C++20 の機能が基本サポートされるようになりました。

- *`.ixx`* ファイルおよび *`.cppm`* ファイルが C++ として認識されるようになり、そのように構文の強調表示機能や IntelliSense で扱われるようになりました。

## <a name="whats-new-for-c-in-visual-studio-version-166"></a>Visual Studio バージョン 16.6 での C++ の新機能

Visual Studio バージョン 16.6 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.6 の新機能](/visualstudio/releases/2019/release-notes-v16.6)に関する記事を参照してください。

- **Doxygen または XML のコメント生成の強化**: 関数の上に `///` または `/**` を入力することで、Doxygen または XML ドキュメント コメントのスタブを自動的に生成します。 クイック ツール ヒントにも表示されるようになりました。

- **Linux または WSL 用 CMake での Ninja のサポート:** WSL またはリモート システム上で CMake プロジェクトをビルドする場合に、基になるジェネレーターとして Ninja を使用します。 Ninja は、Linux または WSL の新しい構成を追加するときの既定のジェネレーターになりました。

- **リモート CMake デバッグ用のデバッグ テンプレート**: リモートの Linux システムまたは WSL 上で gdb を使用して CMake プロジェクトをデバッグするためのテンプレートが簡略化されました。

- **C++20 の概念の初期サポート:** IntelliSense で [C++20 の概念](https://devblogs.microsoft.com/cppblog/c20-concepts-are-here-in-visual-studio-2019-version-16-3/)を認識し、メンバー リストでこれを提示するようになりました。

## <a name="whats-new-for-c-in-visual-studio-version-165"></a>Visual Studio バージョン 16.5 での C++ の新機能

Visual Studio バージョン 16.5 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.5 の新機能](/visualstudio/releases/2019/release-notes-v16.5)に関する記事を参照してください。

- **IntelliCode のチーム入力候補モデルとメンバー変数のサポート:** C++ 開発者が、独自のコードベースで IntelliCode モデルをトレーニングできるようになりました。 チームの作業から恩恵を受けられるため、これはチームの入力候補モデルと呼ばれます。 さらに、メンバー変数の IntelliCode の提案を改善しました。

- **IntelliSense の機能強化:**
  -  標準ライブラリを処理するときに、IntelliSense でよりわかりやすい型名が表示されるようになりました。
  - **Enter**、**Space**、**Tab** 機能による文字のコミット、スニペットの挿入に **Tab** を使用するかどうかの切り替えが可能になりました。 これらの設定は、 **[ツール] > [オプション] > [テキスト エディター] > [C/C++] > [詳細設定] > [IntelliSense]** にあります。

- **コマンド ラインを介した接続マネージャー:** コマンド ラインを使用して、保存されているリモート接続を操作できるようになりました。 これは、新しい開発用マシンのプロビジョニングや、継続的インテグレーションでの Visual Studio の設定のようなタスクに役立ちます。

- **WSL のデバッグと配置:** Visual Studio の WSL のネイティブ サポートを使用して、リモート配置システムからビルド システムを分離します。 WSL 上でネイティブにビルドし、デバッグ用に 2 つ目のリモート システムにビルド成果物を配置できるようになりました。 このワークフローは、CMake プロジェクトと MSBuild ベースの Linux プロジェクトの両方でサポートされています。

- **FIPS 140-2 準拠モードのサポート:** Visual Studio で、リモート Linux システムをターゲットとする C++ アプリケーションを開発するときに、FIPS 140-2 準拠モードがサポートされるようになりました。

- **CMake 言語ファイル用の言語サービス、および CMake プロジェクトの操作の改善:**
  - リモート Linux システムをターゲットとする CMake プロジェクトのソース ファイル コピーが最適化されました。 Visual Studio が、最後にリモートからコピーされたソース セットの "指紋ファイル" を保持し、変更されたファイルの数に基づいて動作を最適化するようになりました。
  -  CMake スクリプト ファイル内の関数、変数、およびターゲットに対して [定義へ移動] や [すべての参照の検索] などのコード ナビゲーション機能が提供されるようになりました。

  - CMake スクリプトを手動で編集することなく、IDE から CMake プロジェクトのソース ファイルとターゲットを追加、削除、名前変更します。 ソリューション エクスプローラーでファイルを追加または削除すると、Visual Studio によって CMake プロジェクトが自動的に編集されます。 ソリューション エクスプローラーのターゲット ビューからプロジェクトのターゲットを追加、削除、名前変更することもできます。

- **Linux プロジェクトの機能強化:** Visual Studio Linux プロジェクトでは、より正確な IntelliSense が使用できるようになり、プロジェクトごとにリモート ヘッダーの同期を制御できるようになりました。

## <a name="whats-new-for-c-in-visual-studio-version-164"></a>Visual Studio バージョン 16.4 での C++ の新機能

Visual Studio バージョン 16.4 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.4 の新機能](/visualstudio/releases/2019/release-notes-v16.4)に関する記事を参照してください。

- Code Analysis では、Clang と MSVC ツールセットのどちらを使用しているかにかかわらず、MSBuild と CMake の両方のプロジェクトで [`Clang-Tidy`](https://aka.ms/cpp/clangtidy) がネイティブにサポートされるようになりました。 clang-tidy チェックは、バックグラウンド コード分析の一部として実行し、エディター内警告 (波線) として示し、エラー一覧に表示できます。

- クロスプラットフォームの開発を開始するのに役立つ[概要](https://devblogs.microsoft.com/cppblog/usability-improvements-for-cmake-in-visual-studio-2019-version-16-4-launch-target-selection-and-overview-pages/)ページが Visual Studio CMake プロジェクトに追加されました。 これらのページを使用すると、Linux システムに接続し、ご利用の CMake プロジェクトに Linux または WSL 構成を追加するのが楽になります。

- [CMake プロジェクト用の起動ドロップダウン メニュー](https://devblogs.microsoft.com/cppblog/usability-improvements-for-cmake-in-visual-studio-2019-version-16-4-launch-target-selection-and-overview-pages/)に、最近使用したターゲットが表示され、フィルター処理できるようになりました。

- [C++/CLI](https://devblogs.microsoft.com/cppblog/an-update-on-cpp-cli-and-dotnet-core/) では、Windows 用の .NET Core 3.1 以降との相互運用がサポートされるようになりました。

- メモリ エラーの検出に役立つ C++ コードのランタイム インスツルメンテーションのために、Windows 上の MSVC でコンパイルされたプロジェクトに対して [ASan](https://aka.ms/cpp/asanmsvc) を有効にできるようになりました。

- MSVC の C++ 標準ライブラリに対する更新:
  - C++17:`to_chars()` の一般的精度が実装され、[P0067R5](https://wg21.link/P0067R5) の基本文字列変換 (charconv) が完了しました。 これにより、C++17 標準のすべてのライブラリ機能の実装が完了します。
  - C++20:[P1754R1](https://wg21.link/P1754R1) の名前変更概念が standard_case に実装されました。 最新の C++ Working Draft のプレビュー機能を含めるには、 **`/std:c++latest`** コンパイラ オプションを使用します。 このオプションは、**C++ 言語の標準** プロパティを使用して、 **[構成プロパティ] > [C/C++] > [言語]** プロジェクトのプロパティ ページで設定することもできます。

- [C++ Build Insights](../build-insights/get-started-with-cpp-build-insights.md) という名前の新しいツールのコレクションを使用できるようになりました。 この発表の詳細については、[C++ チーム ブログ](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/)を参照してください。

## <a name="whats-new-for-c-in-visual-studio-version-163"></a>Visual Studio バージョン 16.3 での C++ の新機能

Visual Studio バージョン 16.3 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.3 の新機能](/visualstudio/releases/2019/release-notes-v16.3)に関する記事を参照してください。

- C++ 開発者は、キーボード ショートカット **Ctrl + K**、**Ctrl + /** キーを使用して行コメントを切り替えることができるようになりました。

- IntelliSense メンバー リストが型修飾子に基づいてフィルター処理されるようになりました。たとえば、`const std::vector` では `push_back` などのメソッドが除外されます。

- 次の C++20 標準ライブラリ プレビュー機能が追加されました ( **`/std:c++latest`** で利用できます)。
  - [P0487R1](https://wg21.link/P0487R1):`operator>>(basic_istream&, CharT*)` の修正
  - [P0616R0](https://wg21.link/P0616R0):`<numeric>` での `move()` の使用
  - [P0758R1](https://wg21.link/P0758R1): `is_nothrow_convertible`
  - [P0734R0](https://wg21.link/P0734R0):概念の C++ 拡張機能
  - [P0898R3](https://wg21.link/P0898R3):標準ライブラリの概念
  - [P0919R3](https://wg21.link/P0919R3):順序なしコンテナーの異種ルックアップ

- 新しい "列挙型規則" 規則セット、追加の `const`、`enum`、および型の規則を含む、[新しい C++ Core Guideline チェック](https://devblogs.microsoft.com/cppblog/new-c-core-check-rules/)。

- 新しい既定のセマンティック色付けスキームでは、ユーザーはコードをひとめでより理解しやすくなります。呼び出し履歴ウィンドウはテンプレート引数を非表示にするように構成でき、C++ IntelliCode は既定でオンになります。

- launch.vs.json および tasks.vs.json の個々のターゲットとタスクで CMakeSettings.json か CppProperties.json か新しい "env" タグを使用して、環境変数を使いデバッグ ターゲットとカスタム タスクを構成します。

- ユーザーは、不足している vcpkg パッケージに対するクイック アクションを使用して、自動的にコンソールを開き、既定の vcpkg インストールにインストールできるようになりました。

- Linux プロジェクト ([CMake](../linux/cmake-linux-project.md) および [MSBuild](../linux/configure-a-linux-project.md)) によって行われるリモート ヘッダー コピーが最適化され、並列で実行されるようになりました。

- Visual Studio の [WSL 用ネイティブ サポート](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)により、MSBuild ベースの Linux プロジェクトの並列ビルドがサポートされるようになりました。

- ユーザーは、Linux メイクファイル プロジェクトを使用してリモート システムに配置するローカル ビルド出力の一覧を指定できるようになりました。

- [CMake 設定エディター](https://devblogs.microsoft.com/cppblog/introducing-the-new-cmake-project-settings-ui/)の設定の説明に、さらに詳しいコンテキストと役立つドキュメントへのリンクが含まれるようになりました。

- IntelliCode の C++ 基本モデルが既定で有効になりました。 この設定を変更するには、 **[ツール]**  >  **[オプション]**  >  **[IntelliCode]** の順に移動します。

## <a name="whats-new-for-c-in-visual-studio-version-162"></a>Visual Studio バージョン 16.2 での C++ の新機能

Visual Studio バージョン 16.2 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.2 の新機能](/visualstudio/releases/2019/release-notes-v16.2)に関する記事を参照してください。

- Clang で構成されているローカルの CMake プロジェクトの場合、コード分析で実行された clang-tidy チェックがバックグラウンド コード分析の一部としてエディター内警告 (波線) とエラー一覧に表示されるようになりました。

- C++ 17 の [P0067R5](https://wg21.link/P0067R5) 基本文字列変換の `<charconv>` ヘッダーが次のように更新されました。
  - `chars_format::fixed` と `chars_format::scientific` の桁数に浮動小数点 `to_chars()` のオーバーロードが追加されました (`chars_format::general precision` は一部で未実装です)
  - `chars_format::fixed` の最短が最適化

- 次の C++20 標準ライブラリ プレビュー機能が追加されました。
  - **`/std:c++latest`** で使用可能:
    - [P0020R6](https://wg21.link/P0020R6): `atomic<floating-point>`
    - [P0463R1](https://wg21.link/P0463R1): エンディアン列挙型
    - [P0482R6](https://wg21.link/P0482R6): UTF-8 文字と文字列用の `char8_t` 型
    - [P0653R2](https://wg21.link/P0653R2): ポインターを生ポインターに変換するための `to_address()`
  - `/std:c++17` と `/std:c++latest` で使用可能:
    - [P0600R1](https://wg21.link/P0600R1): ライブラリの `[[nodiscard]]`
  - 無条件で使用可能:
    - [P0754R2](https://wg21.link/P0754R2): `<version>` ヘッダー
    - [P0771R1](https://wg21.link/P0771R1): `std::function` の移動は `noexcept` にする必要があります

- Windows SDK は、Windows 用 CMake および Linux 用 CMake のコンポーネントと依存しなくなりました。

- [C++ リンカー](https://aka.ms/cpp/162linker)の機能強化により、繰り返しビルド時間の入力の大部分が大幅に改善しました。 **`/DEBUG:FAST`** と **`/INCREMENTAL`** の時間は平均で 2 倍高速になり、 **`/DEBUG:FULL`** は現在 3 から 6 倍高速になりました。

## <a name="whats-new-for-c-in-visual-studio-version-161"></a>Visual Studio バージョン 16.1 での C++ の新機能

Visual Studio バージョン 16.1 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.1 の新機能](/visualstudio/releases/2019/release-notes-v16.1)に関する記事を参照してください。

### <a name="c-compiler"></a>C++ コンパイラ

- C++ コンパイラに次の C++ 20 プレビュー機能が実装され、 **`/std:c++latest`** で使用できるようになりました。
  - 明示的なテンプレート引数を含む関数呼び出し式の引数依存照合を使用する、関数テンプレートの検索機能が強化されました ([P0846R0](http://wg21.link/p0846r0))。
  - 初期化が指定されました ([P0329R4](https://wg21.link/p0329r4))。これにより、集約の初期化で特定のメンバーを選択できるようになります (たとえば、`Type t { .member = expr }` 構文を使用します)。

- ラムダ サポートが見直され、長期にわたる多くのバグに対処できるようになりました。 **`/std:c++latest`** の使用時に、既定でこの変更が有効になります。 **`/std:c++17`** 言語モードおよび既定の ( **`/std:c++14`** ) モードでは、 **`/experimental:newLambdaProcessor`** を使用することで新しいパーサーを有効にできます (例: `/std:c++17 /experimental:newLambdaProcessor`)。

### <a name="c-standard-library-improvements"></a>C++ 標準ライブラリの機能強化

- C++ 標準ライブラリの実装に、次の C++20 プレビュー機能が追加されました。これらは **`/std:c++latest`** で使用できます。
  - `basic_string` と `basic_string_view` 向けの `starts_with` と `ends_with`。
  - 連想コンテナーの `contains`。
  - `list` と `forward_list` の `remove`、`remove_if`、および `unique` で `size_type` が返されるようになりました。
  - `shift_left` および `shift_right` が `<algorithm>` に追加されました。

### <a name="c-ide"></a>C++ IDE

#### <a name="intellicode-for-c"></a>C++ 向けの IntelliCode

IntelliCode がオプションのコンポーネントとして **C++ によるデスクトップ開発** ワークロードに付属するようになりました。 詳細については、[Visual Studio 2019 に付属する強化された C++ IntelliCode](https://devblogs.microsoft.com/cppblog/improved-c-intellicode-now-ships-with-visual-studio-2019/) に関するページをご覧ください。

IntelliCode では、独自の広範なトレーニングとコード コンテキストを使用して、使用される可能性が最も高いものが入力候補一覧の一番上に配置されます。 多くの場合、一覧を見るとき下にスクロールする必要がなくなります。 C++ の場合、標準ライブラリのような一般的なライブラリを使用しているときには、IntelliCode からほとんどのヘルプが提供されます。

プレビューの IntelliCode 機能 (カスタム モデル、C++ サポート、および EditorConfig 推論) は既定で無効になっています。 それらを有効にするには、 **[ツール] > [オプション] > [IntelliCode] > [全般]** にアクセスします。 このバージョンの IntelliCode では精度が向上し、free 関数のサポートが含まれています。 詳細については、「[AI-Assisted Code Completion Suggestions Come to C++ via IntelliCode](https://devblogs.microsoft.com/cppblog/cppintellicode/)」 (AI によるコード入力支援機能が IntelliCode 経由で C++ でも利用可能に) を参照してください。

#### <a name="quick-info-improvements"></a>クイック ヒントの機能強化

- クイック ツールヒントで、エディターのセマンティクスの色づけが考慮されるようになりました。 また、 **[オンラインで検索]** リンクも新しくなりました。カーソルを置いたコード コンストラクターについて詳しく学習するためのオンライン ドキュメントを検索できます。 赤い波線が引かれているコードについては、クイック ヒントで提供されるリンクによってオンラインでエラーを検索します。 この方法では、自分のブラウザーにメッセージを再入力する必要はありません。 詳細については、「[Quick Info Improvements in Visual Studio 2019:Colorization and Search Online (Visual Studio 2019 のクイック ヒントの機能強化: 色づけとオンライン検索)](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/)」をご覧ください。

#### <a name="general-improvements"></a>全般的な機能強化

- テンプレート バーでは、コードベース内での該当のテンプレートのインスタンス化に基づいて、ドロップダウン メニューを入力できます。

- vcpkg でインストール可能な足りない `#include` ディレクティブを示す電球、および CMake `find_package` ディレクティブの利用可能なパッケージのオートコンプリート。

- C++ プロジェクトの **[全般]** プロパティ ページが変更されました。 一部のオプションが、新しい **[詳細設定]** ページに一覧表示されるようになりました。 **[詳細設定]** ページには、優先するツールセット アーキテクチャ、デバッグ ライブラリ、MSVC ツールセットのマイナー バージョン、および Unity (jumbo) ビルド用の新しいプロパティも含まれています。

### <a name="cmake-support"></a>CMake サポート

- Visual Studio に付属する CMake バージョンが 3.14 に更新されました。 このバージョンでは、ファイルベースの IDE 統合 API だけでなく、Visual Studio 2019 プロジェクトをターゲットとする MSBuild ジェネレーターの組み込みサポートが追加されています。

- CMake 設定エディターに対する機能強化が追加されました。これには、既存のキャッシュからの Linux 用 Windows サブシステム (WSL) および構成のサポート、既定のビルドおよびインストール ルートの変更、Linux CMake 構成での環境変数のサポートが含まれます。

- 組み込みの CMake コマンド、変数、およびプロパティの入力候補とクイック ヒントにより、 *`CMakeLists.txt`* ファイルの編集が簡単になりました。

- Clang/LLVM を使った CMake プロジェクトの編集、ビルド、デバッグのサポートが統合されました。 詳細については、「[Clang/LLVM Support in Visual Studio (Visual Studio での Clang/LLVM のサポート)](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/)」をご覧ください。

### <a name="linux-and-the-windows-subsystem-for-linux"></a>Linux と Windows Subsystem for Linux

- Linux および CMake クロスプラットフォーム プロジェクトでの [AddressSanitizer (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) がサポートされるようになりました。 詳細については、「[AddressSanitizer (ASan) for the Linux Workload in Visual Studio 2019 (Visual Studio 2019 の Linux ワークロード用の AddressSanitizer (ASan))](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/)」をご覧ください。

- Linux 用 Windows サブシステム (WSL) で C++ を使うための Visual Studio サポートが統合されました。 Visual Studio 内で C++ によって、ローカルの Linux 用 Windows サブシステム (WSL) のインストールをネイティブに使用できるようになりました。追加の構成や SSH 接続は必要ありません。 詳細については、「[C++ with Visual Studio 2019 and Windows Subsystem for Linux (WSL) (Visual Studio 2019 と Windows Subsystem for Linux (WSL) を使った C++)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)」をご覧ください。

### <a name="code-analysis"></a>コード分析

- 初期化されていない変数のチェックに対する新しいクイック修正が追加されました。 Code Analysis の警告 [C6001: 初期化されていないメモリ &lt;変数&gt; の使用](../code-quality/c6001.md)および [C26494 VAR_USE_BEFORE_INIT](../code-quality/c26494.md) が、該当の行にある電球メニューから使用できます。 これらは、Microsoft ネイティブ最小規則セットと C++ Core Check 型の規則セットそれぞれにおいて、既定で有効になっています。 詳細については、「[New code analysis quick fixes for uninitialized memory (C6001) and use before init (C26494) warnings (初期化されていないメモリ (C6001) と初期化前の使用 (C26494) 警告に関するコード分析の新しいクイック修正)](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/)」をご覧ください。

### <a name="remote-builds"></a>リモート ビルド

- MSBuild および CMake プロジェクトの両方において、Linux をターゲットとする場合に、リモート ビルド マシンをリモート デバッグ マシンから分離できるようになりました。

- リモート接続のログ記録が強化されたことで、クロスプラットフォーム開発における問題が診断しやすくなります。

## <a name="whats-new-for-c-in-visual-studio-version-160"></a>Visual Studio バージョン 16.0 での C++ の新機能

Visual Studio バージョン 16.0 での新機能とバグ修正の概要については、[Visual Studio 2019 バージョン 16.0 の新機能](/visualstudio/releases/2019/release-notes-v16.0)に関する記事を参照してください。

### <a name="c-compiler"></a>C++ コンパイラ

- C++17 機能と正確性の修正に関するサポート強化に加え、モジュールやコルーチンなど、C++20 機能の実験的サポート。 詳しくは、「[C++ Conformance Improvements in Visual Studio 2019](cpp-conformance-improvements.md)」(Visual Studio 2019 での C++ 準拠の強化) をご覧ください。

- [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) オプションには現在、3 方向比較のための C++20 演算子 **`<=>`** ("宇宙船") の初期サポートなど、必ずしも完全ではない C++20 機能が含まれています。

- C++ コンパイラ スイッチ [`/Gm`](../build/reference/gm-enable-minimal-rebuild.md) は現在、非推奨になっています。 ご自分のビルド スクリプト内の **`/Gm`** スイッチが明示的に定義されている場合は、それを無効にすることを検討してください。 ただし、"警告をエラーとして扱う" ([`/WX`](../build/reference/compiler-option-warning-level.md)) を使用しているとき、 **`/Gm`** の非推奨化に関する警告はエラーとして扱われないので無視してもかまいません。

- MSVC により、 **`/std:c++latest`** フラグの下で C++20 標準ドラフトの機能の実装が開始されたため、 **`/std:c++latest`** と **`/clr`** (すべてのフレーバー)、 **`/ZW`** 、 **`/Gm`** との互換性がなくなりました。 Visual Studio 2019 では、`/clr`、`/ZW`、または `/Gm` を使ってコンパイルする場合は `/std:c++17` または `/std:c++14` モードを使ってください (ただし、前の項目を確認してください)。

- C++ コンソール アプリとデスクトップ アプリに対して、プリコンパイル済みヘッダーが既定では生成されなくなりました。

#### <a name="codegen-security-diagnostics-and-versioning"></a>コード生成、セキュリティ、診断、バージョン管理

Spectre Variant 1 の軽減策サポートを提供するため、[`/Qspectre`](../build/reference/qspectre.md) を使用した分析が強化されました ([CVE-2017-5753](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753))。 詳細については、「[Spectre Mitigations in MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)」 (MSVC の Spectre 軽減策) を参照してください。

### <a name="c-standard-library-improvements"></a>C++ 標準ライブラリの機能強化

- 追加の C++17 と C++20 のライブラリ機能と正確性の修正の実装。 詳しくは、「[C++ Conformance Improvements in Visual Studio 2019](cpp-conformance-improvements.md)」(Visual Studio 2019 での C++ 準拠の強化) をご覧ください。

- Clang-Format が C++ 標準ライブラリのヘッダーに適用され、読みやすさが向上しました。

- Visual Studio で C++ の [マイ コードのみ] がサポートされるようになったため、同じ効果を実現するため標準ライブラリで `std::function` と `std::visit` のカスタム メカニズムを提供する必要がなくなりました。 そのメカニズムが削除されても、ユーザーが確認できる影響はほとんどありません。 ただし、コンパイラにより、\<type_traits> または \<variant> の行 15732480 または 16707566 上の問題を示す診断が生成されなくなります。

### <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>コンパイラと標準ライブラリでのパフォーマンス/スループットの向上

- リンカーによるファイル I/O の処理や PDB タイプのマージと作成のリンク時間など、ビルドのスループットが改善されました。

- OpenMP SIMD ベクター化の基本的なサポートが追加されました。 これは新しいコンパイラ スイッチ **`/openmp:experimental`** を使用して有効にできます。 このオプションにより、`#pragma omp simd` で注釈が付けられたループをベクター化できる可能性があります。 ベクター化は保証されておらず、注釈が付けられていてもベクター化されていないループに対しては警告が報告されます。 SIMD 句はサポートされていません。無視され、警告が報告されます。

- 新しいインライン展開コマンド ライン スイッチ **`/Ob3`** が追加されました。これは、 **`/Ob2`** より積極的なバージョンです。 **`/O2`** (速さのためにバイナリを最適化) は引き続き、既定で **`/Ob2`** を意味します。 コンパイラのインライン展開が十分に積極的でない場合、 **`/O2 -Ob3`** を渡すことを検討してください。

- Short Vector Math Library (SVML) 組み込み関数のサポートが追加されました。 これらの関数では、128 ビット、256 ビット、または 512 ビットの同等のベクターが計算されます。 これらが追加されたことで、数値演算ライブラリ関数および整数除算などの他の特定の演算の呼び出しを含むループの手動ベクター化がサポートされました。 サポートされている関数の定義については、[Intel 組み込みガイド](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML)をご覧ください。

- 新規および改良された最適化:

  - float と integer の両方の形式に対する、SIMD ベクター組み込み関数を使用する式の定数折りたたみと計算の簡略化。

  - 常に true または false になることがわかっている分岐を削除するために制御フロー (if/else/switch ステートメント) から情報を抽出するためのいっそう強力な分析。

  - SSE2 ベクター命令を使用するための memset アンローリングの向上。

  - 意味のない構造体/クラスのコピーの削除の向上、特に値渡しの C++ プログラムの場合。

  - `std::copy` または `std::vector` および `std::string` 構築など、`memmove` を利用したコードの最適化の改善。

- 標準ライブラリで直接インクルードされない部分のコンパイルを回避するよう、標準ライブラリの物理的設計を最適化しました。 この変更により、\<vector> しか含まれない空のファイルをビルドする時間が半分になります。 結果として、以前は間接的に含まれていたヘッダーの `#include` ディレクティブの追加が必要になることがあります。 たとえば、`std::out_of_range` を使うコードでは、`#include <stdexcept>` の追加が必要になることがあります。 ストリーム挿入演算子を使うコードでは、`#include <ostream>` の追加が必要になることがあります。 その利点は、実際に \<stdexcept> または \<ostream> コンポーネントを使う変換単位のみで、それらをコンパイルするスループットのコストがかかるようになることです。

- 標準ライブラリのさらに多くの場所で `if constexpr` が適用され、コピー操作、反転や回転のような順列、および並列アルゴリズムのライブラリにおいて、スループットが向上し、コードのサイズが削減されました。

- 標準ライブラリで内部的に `if constexpr` を使うようになり、C++14 モードであってもコンパイル時間が短縮されます。

- 並列アルゴリズムのライブラリの実行時の動的リンク検出で、関数ポインターの配列を格納するためにページ全体が使われなくなりました。 このメモリを読み取り専用にすることは、セキュリティのために重要だと見なされなくなりました。

- `std::thread` コンストラクターでスレッドの開始が待機されなくなり、基になる C ライブラリ `_beginthreadex` と指定された呼び出し可能オブジェクトの間にそれほど多くの関数呼び出しのレイヤーが挿入されなくなりました。 以前の `std::thread` では、`_beginthreadex` と指定された呼び出し可能オブジェクトの間に 6 つの関数が配置されていました。 この数は 3 つのみに減りました。そのうちの 2 つは単に `std::invoke` です。 また、この変更により、`std::thread` の作成とちょうど同じ時間にシステム クロックが変更された場合に `std::thread` のコンストラクターが応答を停止するという、あいまいなタイミングのバグも解決されます。

- `std::hash<std::filesystem::path>` を実装する際に導入された `std::hash` のパフォーマンス低下を修正しました。

- 標準ライブラリのいくつかの場所で、正確性を実現するために catch ブロックの代わりにデストラクターが使われるようになりました。 この結果、デバッガーの操作性が向上します。標準ライブラリの影響を受けた場所を通じてスローした例外は、再スローではなく、その元のスロー サイトからスローされたものとして表示されるようになります。 すべての標準ライブラリ キャッチ ブロックが削除されたわけではありません。 MSVC の今後のリリースでは、catch ブロック数が減ると予想されます。

- `noexcept` 関数内の条件付きスローが原因となる `std::bitset` の準最適な codegen が、スローのパスを取り除くことで修正されました。

- `std::list` および `std::unordered_*` ファミリで、より多くの場所で内部的に非デバッグの反復子が使われます。

- `std::list` のいくつかのメンバーが変更され、リスト ノードを開放して再割り当てする代わりに、可能であればそれらを再利用するようになりました。 たとえば、既にサイズ 3 の `list<int>` があるとします。`assign(4, 1729)` を呼び出すと、最初の 3 つのリスト ノードの `int` 値が上書きされ、1 つの新しいリスト ノードが値 1729 と共に割り当てられるようになりました。

- 標準ライブラリのすべての `erase(begin(), end())` 呼び出しが `clear()` に変更されました。

- `std::vector` で、特定のケースでより効率的に要素を初期化および消去できるようになりました。

- `std::variant` が改善され、最適化がより簡単になりました。結果的に、より良いコードが生成されます。 `std::visit` を利用することで、コードのインライン展開が改善されます。

### <a name="c-ide"></a>C++ IDE

#### <a name="live-share-c-support"></a>Live Share C++ サポート

[Live Share](/visualstudio/liveshare/) は C++ 対応になりました。Visual Studio または Visual Studio Code を使用する開発者はリアルタイムで共同作業できます。 詳細については、「[Announcing Live Share for C++: Real-Time Sharing and Collaboration](https://devblogs.microsoft.com/cppblog/cppliveshare/)」 (C++ 向け Live Share のお知らせ: リアルタイムの共有と共同作業) を参照してください

#### <a name="template-intellisense"></a>テンプレート IntelliSense

**テンプレート バー** で、モーダル ウィンドウではなく **ピーク ウィンドウ** UI が使用され、入れ子になったテンプレートがサポートされ、**ピーク ウィンドウ** に既定の引数が設定されるようになりました。 詳細については、「[Template IntelliSense Improvements for Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 のテンプレート IntelliSense 改善) を参照してください。 **テンプレート バー** の **[直前に使用]** ドロップダウンでは、前に使用したサンプル引数のセットを簡単に切り替えることができます。

#### <a name="new-start-window-experience"></a>新しいスタート画面のエクスペリエンス

IDE を起動すると、新しい [スタート] ウィンドウが表示されます。 最近使ったプロジェクトを開く、ソース管理からコードを複製する、ローカル コードをソリューションまたはフォルダーとして開く、または新しいプロジェクトを作成するオプションがあります。 [新しいプロジェクト] ダイアログも改善され、検索第一でフィルタリング可能になりました。

#### <a name="new-names-for-some-project-templates"></a>一部のプロジェクト テンプレートの新しい名前

更新した [新しいプロジェクト] ダイアログ ボックスに合わせて、プロジェクト テンプレートの名前と説明をいくつか変更しました。

#### <a name="various-productivity-improvements"></a>さまざまな生産性の向上

Visual Studio 2019 では、コードをもっと簡単に、もっと直観的に記述できるように次の機能が追加されました。

- クイック修正:
  - 不足している `#include` の追加
  - `NULL` ～ `nullptr`
  - 不足しているセミコロンの追加
  - 不足している名前空間または範囲の解決
  - 無効な間接参照オペランドを置換 (`*` を `&` に、`&` を `*` に)
- 右括弧にカーソルを置くと、ブロックのクイック インフォが表示
- ヘッダー/コード ファイルの表示
- `#include` の [定義へ移動] でファイルが開く

詳細については、「[C++ Productivity Improvements in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 の C++ 生産性向上) を参照してください。

### <a name="cmake-support"></a>CMake サポート

- CMake 3.14 のサポート

- Visual Studio では、CMakeGUI などの外部ツール、カスタマイズされたメタビルド システム、cmake.exe をそれ自体で呼び出すビルド スクリプトによって生成された既存の CMake キャッシュを開けるようになりました。

- 強化された IntelliSense パフォーマンス。

- 新しい設定エディターでは、CMakeSettings.json ファイルの手動編集の代わりになるもの、CMakeGUI と同等の機能が提供されます。

- Visual Studio では、Linux コンピューター上に互換性のある CMake のバージョンがあるかどうかが検出されることにより、Linux で CMake による C++ の開発を始めやすくなりました。 ない場合は、インストールすることができます。

- CMakeSettings での互換性のない設定 (アーキテクチャの不一致や、互換性のない CMake ジェネレーターの設定など) に対しては、JSON エディターおよびエラー一覧のエラーで波線が表示されます。

- `vcpkg integrate install` を実行した後は、vcpkg ツール チェーンが自動的に検出され、IDE で開かれる CMake プロジェクトに対して有効になります。 この動作は、CMakeSettings で空のツールチェーン ファイルを指定することによりオフにできます。

- CMake プロジェクトでは、"マイ コードのみ" デバッグが既定で有効になるようになりました。

- CMake プロジェクトのスタティック分析の警告をバックグラウンドで処理し、エディターに表示できるようになりました。

- CMake プロジェクトのビルドと構成の "開始" および "終了" に関するいっそう明確なメッセージと、Visual Studio のビルドの進行状況 UI のサポート。 さらに、出力ウィンドウに表示される CMake のビルドおよび構成に関するメッセージの詳細レベルをカスタマイズできる CMake の詳細さの設定が、 **[ツール] の [オプション]** に追加されました。

- CMake のコマンド ラインを手動で変更することなくツールチェーンを指定するための `cmakeToolchain` の設定が、CMakeSettings.json でサポートされるようになりました。

- 新しい **[すべてビルド]** メニューのショートカット **Ctrl+Shift+B**。

### <a name="incredibuild-integration"></a>IncrediBuild の統合

IncrediBuild がオプションのコンポーネントとして **C++ によるデスクトップ開発** ワークロードに含まれるようになりました。 IncrediBuild のビルド モニターは、Visual Studio IDE に完全に統合されています。 詳細については、「[IncrediBuild のビルド モニターと Visual Studio 2019 を使ってビルドを視覚化する](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/)」を参照してください。

### <a name="debugging"></a>デバッグ

- Windows 上で実行される C++ アプリケーションの場合、PDB ファイルは別個の 64 ビット プロセスで読み込まれるようになりました。 この変更により、デバッガーでメモリ不足のために発生するさまざまなクラッシュが解決されます。 たとえば、多数のモジュールと PDB ファイルを含むアプリケーションをデバッグする場合などです。

- **[ウォッチ]** 、 **[自動]** 、 **[ローカル]** ウィンドウで検索が有効になります。

### <a name="windows-desktop-development-with-c"></a>C++ による Windows デスクトップ開発

- 次の C++ ATL/MFC ウィザードは使用できなくなりました。

  - ATL COM+ 1.0 コンポーネント ウィザード
  - ATL Active Server Page コンポーネント ウィザード
  - ATL OLE DB プロバイダー ウィザード
  - ATL プロパティ ページ ウィザード
  - ATL OLE DB コンシューマー ウィザード
  - MFC ODBC コンシューマー
  - ActiveX コントロールの MFC クラス
  - TypeLib からの MFC クラス。

  これらのテクノロジのサンプル コードは、Microsoft Docs および VCSamples GitHub リポジトリにアーカイブされています。

- Windows 8.1 ソフトウェア開発キット (SDK) は、Visual Studio インストーラーでは使用できなくなりました。 最新の Windows 10 SDK に C++ プロジェクトをアップグレードすることをお勧めします。 8\.1 に対するハードな依存関係がある場合は、Windows SDK アーカイブからダウンロードできます。

- 最新の C++ ツールセットでは、Windows XP を対象にできなくなります。 VS 2017 レベルの MSVC コンパイラとライブラリによる VS の対象指定はまだサポートされており、[個別のコンポーネント] を使用してインストールできます。

- ドキュメントでは、Visual C++ ランタイムの配置に対してマージ モジュールを使用しないよう強く推奨されています。 このリリースでは、MSM を非推奨にするための追加手順が行われています。 VCRuntime の集中配置を MSM から再頒布可能パッケージに移行することを検討してください。

### <a name="mobile-development-with-c-android-and-ios"></a>C++ によるモバイル開発 (Android および iOS)

C++ Android エクスペリエンスは、既定では Android SDK 25 および Android NDK 16b となりました。

### <a name="clangc2-platform-toolset"></a>Clang/C2 プラットフォーム ツールセット

実験段階の Clang/C2 コンポーネントが削除されました。 `/permissive-` および `/std:c++17` に完全に準拠した C++ 用の MSVC ツールセットを使用するか、Windows 用の Clang/LLVM ツールチェーンを使用します。

### <a name="code-analysis"></a>コード分析

- コード分析がバックグラウンドで自動的に実行されるようになりました。 エディターでの入力時に緑色の波線で警告が表示されます。 詳細については、「[In-editor code analysis in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 のエディター内コード分析) を参照してください。

- \<mutex> ヘッダーのよく知られている Standard Library タイプのための新しい試験段階 ConcurrencyCheck 規則。 詳細については、「[Concurrency Code Analysis in Visual Studio 2019](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/)」 (Visual Studio 2019 のコンカレンシー コード分析) を参照してください。

- [Lifetime プロファイル チェッカー](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)の更新された部分的な実装。これは未解決のポインターと参照を検出します。 詳細については、「[Lifetime Profile Update in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 の Lifetime プロファイル更新) を参照してください。

- [C26138](../code-quality/c26138.md)、[C26810](../code-quality/c26810.md)、[C26811](../code-quality/c26811.md) や、試験段階規則 [C26800](../code-quality/c26800.md) など、コルーチン関連のチェックの追加。 詳細については、「[New Code Analysis Checks in Visual Studio 2019: use-after-move and coroutine](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/)」 (Visual Studio 2019 の新しいコード分析チェック: use-after-move とコルーチン) を参照してください。

### <a name="unit-testing"></a>単体テスト

マネージド C++ テスト プロジェクト テンプレートは使用できなくなります。 既存のプロジェクトでは、マネージド C++ テスト フレームワークを引き続き使用できます。 新しい単体テストでは、Visual Studio でテンプレートが提供されているネイティブ テスト フレームワークのいずれか (MSTest、Google Test) またはマネージド C# テスト プロジェクト テンプレートの使用を検討してください。
