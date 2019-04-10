---
title: Visual Studio 2019 での C++ の新機能
ms.date: 04/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 493b96a8ce3359cc18287adbae8cbd6c374671ec
ms.sourcegitcommit: b72a10a7b12e722fd91a17406b91b270026f763a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899408"
---
<!--NOTE all https:// links to docs.microsoft.com need to be converted to site-relative links prior to publishing-->

# <a name="whats-new-for-c-in-visual-studio-2019"></a>Visual Studio 2019 での C++ の新機能

Visual Studio 2019 には、Microsoft C++ 環境に対する多くの更新プログラムと修正プログラムが導入されています。 コンパイラとツールに存在したたくさんのバグと報告された問題を修正してきました。その多くは、**[フィードバックの送信]** の [[問題の報告]](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) オプションおよび [[提案の送信]](https://developercommunity.visualstudio.com/spaces/62/index.html) オプションを通じてお客様から寄せられたものです。 バグ レポートをお寄せいただきありがとうございました。 Visual Studio 全体の新機能の詳細については、「[Visual Studio の新機能](/visualstudio/ide/whats-new-visual-studio-2019)」を参照してください。

## <a name="c-compiler"></a>C++ コンパイラ

- `/std:c++latest` オプションには現在、3 方向比較のための C++20 演算子 <=> ("宇宙船") の初期サポートなど、必ずしも完全ではない C++20 機能が含まれています。

- [P0941R2 - 機能テスト マクロ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html)は完全であり、`__has_cpp_attribute` がサポートされています。 機能テスト マクロはすべての標準モードでサポートされています。

- [C++20 P1008R1 - ユーザー宣言コンストラクターによる集計の禁止](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf)も完全です。

- C++17 機能のサポート強化に加え、モジュールやコルーチンなど、C++20 機能の実験的サポート。 詳しくは、「[C++ Conformance Improvements in Visual Studio 2019](../cpp-conformance-improvements.md)」(Visual Studio 2019 での C++ 準拠の強化) をご覧ください。

- C++ コンパイラ スイッチ `/Gm` は現在、非推奨になっています。 ご自分のビルド スクリプト内の `/Gm` スイッチが明示的に定義されている場合は、それを無効にすることを検討してください。 ただし、"警告をエラーとして扱う" (`/WX`) を使用しているとき、`/Gm` の非推奨化に関する警告はエラーとして扱われないので無視してもかまいません。

- C++ コンソール アプリとデスクトップ アプリに対して、プリコンパイル済みヘッダーが既定では生成されなくなりました。

### <a name="codegen-security-diagnostics-and-versioning"></a>コード生成、セキュリティ、診断、バージョン管理

Spectre Variant 1 のリスク軽減サポートを提供するため、`/Qspectre` を使用した分析が強化されました (CVE-2017-5753)。 詳細については、「[Spectre Mitigations in MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)」 (MSVC の Spectre 軽減策) を参照してください。

## <a name="c-standard-library-improvements"></a>C++ 標準ライブラリの機能強化

- [C++20 P0550R2 \(remove_cvref)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf) は完全です。

- C++17 \<charconv> floating-point to_chars() の改善: 最短 chars_format::fixed は 60-80% 速くなり、最短/高精度 chars_format::hex は完全です。

- 実装が並列化されるアルゴリズムが増えました: is_sorted()、is_sorted_until()、is_partitioned()、set_difference()、set_intersection()、is_heap()、is_heap_until()。

- `std::variant` が改善され、最適化がより簡単になりました。結果的に、より良いコードが生成されます。 `std::visit` を利用することで、コードのインライン展開が改善されます。

- clang-format を C++ Standard Library に適用し、読みやすくしました。

- `if constexpr` を利用して一部の標準ライブラリ機能をコンパイルするときのスループットが改善されました。

- 標準ライブラリで #include が使用されない部分のコンパイルを回避するよう、標準ライブラリの物理的設計を最適化しました。\<vector> しか含まれない空のファイルをビルドする時間が半分になります。

## <a name="performancethroughput-fixes"></a>パフォーマンスやスループットの修正

- リンカーによるファイル I/O の処理や PDB タイプのマージと作成のリンク時間など、ビルドのスループットが改善されました。

- OpenMP SIMD ベクター化の基本的なサポートが追加されました。 新しい CL スイッチ `-openmp:experimental` を使用して有効にできます。 このオプションにより、`#pragma omp simd` で注釈が付けられたループをベクター化できる可能性があります。 ベクター化は保証されておらず、注釈が付けられていてもベクター化されていないループに対しては警告が報告されます。 SIMD 句はサポートされていません。無視され、警告が報告されます。

- 新しいインライン展開コマンド ライン スイッチ `-Ob3` が追加されました。これは、`-Ob2` より積極的なバージョンです。 `-O2` (速さのためにバイナリを最適化) は引き続き、既定で `-Ob2` を意味します。 コンパイラのインライン展開が十分に積極的でない場合、`-O2 -Ob3` を渡すことを検討してください。

- 数値演算ライブラリ関数および整数除算などの他の特定の演算の呼び出しを含むループの手動ベクター化をサポートするため、Short Vector Math Library (SVML) 組み込み関数のサポートが追加されました。 これらの関数では、128 ビット、256 ビット、または 512 ビットの同等のベクターが計算されます。 サポートされている関数の定義については、[Intel 組み込みガイド](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML)をご覧ください。

- 新規および改良された最適化:

  - float と integer の両方の形式に対する、SIMD ベクター組み込み関数を使用する式の定数折りたたみと計算の簡略化。

  - 常に true または false になることがわかっている分岐を削除するために制御フロー (if/else/switch ステートメント) から情報を抽出するためのいっそう強力な分析。

  - SSE2 ベクター命令を使用するための memset アンローリングの向上。

  - 意味のない構造体/クラスのコピーの削除の向上、特に値渡しの C++ プログラムの場合。

  - `std::copy` または `std::vector` および `std::string` 構築など、`memmove` を利用したコードの最適化の改善。

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Live Share C++ サポート

[Live Share](/visualstudio/liveshare/) は C++ 対応になりました。Visual Studio または Visual Studio Code を使用する開発者はリアルタイムで共同作業できます。 詳細については、「[Announcing Live Share for C++: Real-Time Sharing and Collaboration](https://devblogs.microsoft.com/cppblog/cppliveshare/)」 (C++ 向け Live Share のお知らせ: リアルタイムの共有と共同作業) を参照してください

### <a name="intellicode-for-c"></a>C++ 向けの IntelliCode

IntelliCode はオプションの拡張機能であり、独自の広範囲なトレーニングとコード コンテキストを使用し、入力候補一覧の上部に使用頻度が高いものを配置します。 多くの場合、一覧を見るとき下にスクロールする必要がなくなります。 C++ の場合、標準ライブラリのような一般的なライブラリを使用しているときには、IntelliCode からほとんどのヘルプが提供されます。 詳細については、「[AI-Assisted Code Completion Suggestions Come to C++ via IntelliCode](https://devblogs.microsoft.com/cppblog/cppintellicode/)」 (AI によるコード入力支援機能が IntelliCode 経由で C++ でも利用可能に) を参照してください。

### <a name="template-intellisense"></a>テンプレート IntelliSense

**テンプレート バー**で、モーダル ウィンドウではなく**ピーク ウィンドウ** UI が使用され、入れ子になったテンプレートがサポートされ、**ピーク ウィンドウ**に既定の引数が設定されるようになりました。 詳細については、「[Template IntelliSense Improvements for Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 のテンプレート IntelliSense 改善) を参照してください。 **テンプレート バー**の **[直前に使用]** ドロップダウンでは、前に使用したサンプル引数のセットを簡単に切り替えることができます。

### <a name="new-start-window-experience"></a>新しいスタート画面のエクスペリエンス

IDE を起動すると、新しい [開始] ウィンドウが開き、最近使用したプロジェクトを開くオプション、ソース管理からコードを複製するオプション、ソリューションまたはフォルダーとしてローカル コードを開くオプション、新しいプロジェクトを作成するオプションが表示されます。 [新しいプロジェクト] ダイアログも改善され、検索第一でフィルタリング可能になりました。

### <a name="new-names-for-some-project-templates"></a>一部のプロジェクト テンプレートの新しい名前

更新した [新しいプロジェクト] ダイアログ ボックスに合わせて、プロジェクト テンプレートの名前と説明をいくつか変更しました。

### <a name="various-productivity-improvements"></a>さまざまな生産性の向上

Visual Studio 2019 では、コードをもっと簡単に、もっと直観的に記述できるように次の機能が追加されました。

- クイック修正:
  - 不足している #include の追加
  - NULL を nullptr に
  - 不足しているセミコロンの追加
  - 不足している名前空間または範囲の解決
  - 無効な間接参照オペランドを置換 (\* を & に、& を \* に)
- 右括弧にカーソルを置くと、ブロックのクイック インフォが表示
- ヘッダー/コード ファイルの表示
- #include の [定義へ移動] でファイルが開く

詳細については、「[C++ Productivity Improvements in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 の C++ 生産性向上) を参照してください。

## <a name="cmake-support"></a>CMake サポート

- Visual Studio では、CMakeGUI などの外部ツール、カスタマイズされたメタビルド システム、cmake.exe をそれ自体で呼び出すビルド スクリプトによって生成された既存の CMake キャッシュを開けるようになりました。

- 強化された IntelliSense パフォーマンス。

- 新しい設定エディターでは、CMakeSettings.json ファイルの手動編集の代わりになるもの、CMakeGUI と同等の機能が提供されます。

- Visual Studio では、Linux コンピューター上に互換性のある CMake のバージョンがあるかどうかが検出され、ない場合は自動的にインストールすることにより、Linux で CMake による C++ の開発を始めやすくなりました。

- CMakeSettings での互換性のない設定 (アーキテクチャの不一致や、互換性のない CMake ジェネレーターの設定など) に対しては、JSON エディターおよびエラー一覧のエラーで波線が表示されます。

- `vcpkg integrate install` を実行した後は、vcpkg ツール チェーンが自動的に検出され、IDE で開かれる CMake プロジェクトに対して有効になります。 この動作は、CMakeSettings で空のツールチェーン ファイルを指定することによりオフにできます。

- CMake プロジェクトでは、"マイ コードのみ" デバッグが既定で有効になるようになりました。

- CMake プロジェクトのスタティック分析の警告をバックグラウンドで処理し、エディターに表示できるようになりました。

- CMake プロジェクトのビルドと構成の "開始" および "終了" に関するいっそう明確なメッセージと、Visual Studio のビルドの進行状況 UI のサポート。 さらに、出力ウィンドウに表示される CMake のビルドおよび構成に関するメッセージの詳細レベルをカスタマイズできる CMake の詳細さの設定が、**[ツール] の [オプション]** に追加されました。

- CMake のコマンド ラインを手動で変更することなくツールチェーンを指定するための `cmakeToolchain` の設定が、CMakeSettings.json でサポートされるようになりました。

- 新しい **[すべてビルド]** メニューのショートカット **Ctrl+Shift+B**。

## <a name="debugging"></a>デバッグ

- Windows 上で実行される C++ アプリケーションの場合、PDB ファイルは別個の 64 ビット プロセスで読み込まれるようになりました。 この変更では、モジュールと PDB ファイルが多数含まれているアプリケーションをデバッグするときにメモリ不足が原因で発生するさまざまなクラッシュに対処しています。

## <a name="windows-desktop-development-with-c"></a>C++ による Windows デスクトップ開発

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

- Visual Studio インストーラーでは Windows 8.1 SDK を使用できなくなりました。 最新の Windows 10 SDK に C++ プロジェクトをアップグレードすることをお勧めします。 8.1 に対するハードな依存関係がある場合は、Windows SDK アーカイブからダウンロードできます。

- 最新の C++ ツールセットでは、Windows XP を対象にできなくなります。 VS 2017 レベルの MSVC コンパイラとライブラリによる VS の対象指定はまだサポートされており、[個別のコンポーネント] を使用してインストールできます。

- ドキュメントでは、Visual C++ ランタイムの配置に対してマージ モジュールを使用しないよう強く推奨されています。 このリリースでは、MSM を非推奨にするための追加手順が行われています。 VCRuntime の集中配置を MSM から再頒布可能パッケージに移行することを検討してください。

## <a name="mobile-development-with-c-android-and-ios"></a>C++ によるモバイル開発 (Android および iOS)

C++ Android エクスペリエンスは、既定では Android SDK 25 および Android NDK 16b となりました。

## <a name="clangc2-platform-toolset"></a>Clang/C2 プラットフォーム ツールセット

実験段階の Clang/C2 コンポーネントが削除されました。 `/permissive-` および `/std:c++17` に完全に準拠した C++ 用の MSVC ツールセットを使用するか、Windows 用の Clang/LLVM ツールチェーンを使用します。

## <a name="code-analysis"></a>コード分析

- コード分析がバックグラウンドで自動的に実行されるようになりました。 エディターでの入力時に緑色の波線で警告が表示されます。 詳細については、「[In-editor code analysis in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 のエディター内コード分析) を参照してください。

- \<mutex> ヘッダーのよく知られている Standard Library タイプのための新しい試験段階 ConcurrencyCheck 規則。 詳細については、「[Concurrency Code Analysis in Visual Studio 2019](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/)」 (Visual Studio 2019 のコンカレンシー コード分析) を参照してください。

- [Lifetime プロファイル チェッカー](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)の更新された部分的な実装。これは未解決のポインターと参照を検出します。 詳細については、「[Lifetime Profile Update in Visual Studio 2019 Preview 2](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/)」 (Visual Studio 2019 プレビュー 2 の Lifetime プロファイル更新) を参照してください。

- C26138、C26810、C26811、試験段階規則 C26800 など、コルーチン関連のチェックを増やしました。 詳細については、「[New Code Analysis Checks in Visual Studio 2019: use-after-move and coroutine](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/)」 (Visual Studio 2019 の新しいコード分析チェック: use-after-move とコルーチン) を参照してください。

## <a name="unit-testing"></a>単体テスト

マネージド C++ テスト プロジェクト テンプレートは使用できなくなります。 既存のプロジェクトでは、マネージド C++ テスト フレームワークを引き続き使用できます。 新しい単体テストでは、Visual Studio でテンプレートが提供されているネイティブ テスト フレームワークのいずれか (MSTest、Google Test) またはマネージド C# テスト プロジェクト テンプレートの使用を検討してください。
