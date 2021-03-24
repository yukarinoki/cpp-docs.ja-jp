---
title: Visual Studio 2017 での C++ の新機能
description: Visual Studio 2017 での Microsoft C/C++ コンパイラとツールにおける新機能と修正プログラム。
ms.date: 03/08/2021
ms.technology: cpp-ide
ms.openlocfilehash: bb99f98482484f46824d16f4e202989b0ec6b8ca
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2021
ms.locfileid: "103147273"
---
# <a name="whats-new-for-c-in-visual-studio-2017"></a>Visual Studio 2017 での C++ の新機能

Visual Studio 2017 には、C++ 環境に対する多くの更新プログラムと修正プログラムが導入されています。 コンパイラとツールで報告された 250 件を超えるバグと問題を修正しました。 その多くは、 **[フィードバックの送信]** の [[問題の報告] および [提案の送信]](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2017&preserve-view=true) オプションを通じてお客様から寄せられたものです。 バグ レポートをお寄せいただきありがとうございました。

Visual Studio 全体の新機能の詳細については、「[Visual Studio 2017 の新機能](/visualstudio/ide/whats-new-visual-studio-2017?view=vs-2017&preserve-view=true)」を参照してください。 Visual Studio 2019 での C++ の新機能については、「[Visual Studio での C++ の新機能](what-s-new-for-visual-cpp-in-visual-studio.md?preserve-view=true&view=msvc-160)」を参照してください。 Visual Studio 2015 以前のバージョンでの C++ の新機能については、「[Visual Studio 2003 から 2015 の Visual C++ の新機能](../porting/visual-cpp-what-s-new-2003-through-2015.md)」を参照してください。 C++ ドキュメントの新着記事については、[Microsoft C++ ドキュメントの新着記事](whats-new-cpp-docs.md)に関するページを参照してください。

## <a name="visual-studio-2017-c-compiler"></a>Visual Studio 2017 C++ コンパイラ

### <a name="c-conformance-improvements"></a>C++ 準拠の強化

このリリースでは、C++ コンパイラと標準ライブラリを更新し、C++ 11 および C++ 14 機能のサポートを強化しました。 また、C++17 規格に組み込まれる予定の機能の一部も予備的にサポートされています。 詳しくは、「[C++ Conformance Improvements in Visual Studio 2017](cpp-conformance-improvements.md)」(Visual Studio 2017 での C++ 準拠の強化) をご覧ください。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

コンパイラでは C++17 の新機能の約 75% がサポートされています。その中には構造化バインド、 **`constexpr`** ラムダ、`if constexpr`、インライン変数、フォールド式、型システムへの **`noexcept`** の追加が含まれます。 これらの機能は、 **`/std:c++17`** オプションで使用できます。 詳細については、[Visual Studio 2017 での C++ 準拠の強化](cpp-conformance-improvements.md)に関するページをご覧ください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

Visual Studio バージョン 15.7 の MSVC コンパイラ ツールセットが、C++ 標準に準拠となりました。 詳細については、「[Announcing: MSVC Conforms to the C++ Standard (発表: MSVC の C++ への準拠)](https://devblogs.microsoft.com/cppblog/announcing-msvc-conforms-to-the-c-standard/)」および [Microsoft C++ 言語の準拠](./visual-cpp-language-conformance.md)に関するページを参照してください。

##### <a name="visual-studio-2017-version-158"></a>Visual Studio 2017 バージョン 15.8

[`/experimental:preprocessor`](../build/reference/experimental-preprocessor.md) コンパイラ スイッチを使用すると、新しい実験的な MSVC プリプロセッサが有効になり、最終的に該当するすべての C および C++ 標準に準拠するようになります。 詳細については、「[MSVC の新しいプリプロセッサの概要](../preprocessor/preprocessor-experimental-overview.md)」を参照してください。

### <a name="new-compiler-options"></a>新しいコンパイラ オプション

- [`/permissive-`](../build/reference/permissive-standards-conformance.md):すべての厳密な標準準拠コンパイラ オプションを有効にして、ほとんどの Microsoft 固有コンパイラ拡張機能 (ただし、たとえば `__declspec(dllimport)` は除きます) を無効にします。 このオプションは、Visual Studio 2017 バージョン 15.5 では既定でオンになっています。  **`/permissive-`** 準拠モードは、2 フェーズの名前参照に対応しています。 詳細については、[Visual Studio での C++ 準拠の強化](cpp-conformance-improvements.md)に関するページをご覧ください。

- [`/diagnostics`](../build/reference/diagnostics-compiler-diagnostic-options.md):診断エラーまたは警告の場所が、行番号のみ、行番号と列、または行番号と列という 3 種類の方法で表示されます。また、問題のあるコード行の下にキャレットが表示されます。

- [`/debug:fastlink`](../build/reference/debug-generate-debug-info.md):すべてのデバッグ情報を PDB ファイルにコピーしないことで、インクリメンタル リンク時間を最大で 30% 高速化します (Visual Studio 2015 と比較した場合)。 代わりに、PDB ファイルは実行可能ファイルの作成に使われたオブジェクトとライブラリ ファイルのデバッグ情報を参照します。 「[VS "15" での `/Debug:fastlink` による C++ ビルド サイクルの高速化](https://devblogs.microsoft.com/cppblog/faster-c-build-cycle-in-vs-15-with-debugfastlink/)」と「[Visual Studio で C++ のビルドを高速化するための推奨事項](https://devblogs.microsoft.com/cppblog/recommendations-to-speed-c-builds-in-visual-studio/)」を参照してください。

- Visual Studio 2017 では、[`/await`](../build/reference/await-enable-coroutine-support.md) を指定して [`/sdl`](../build/reference/sdl-enable-additional-security-checks.md) を使用できます。 コルーチンでの [`/RTC`](../build/reference/rtc-run-time-error-checks.md) の制限がなくなりました。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- [`/std:c++14` および `/std:c++latest`](../build/reference/std-specify-language-standard-version.md):これらのコンパイラ オプションを使用すると、プロジェクトで ISO C++ プログラミング言語の特定のバージョンにオプトインできます。 新しいドラフト標準機能のほとんどは、 **`/std:c++latest`** オプションによって保護されています。

- [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) を使用すると、コンパイラによって実装された C++17 機能セットが有効になります。 このオプションを指定すると、C++ 17 後の機能 (ワーキング ドラフトの新しいバージョンで変更または追加された機能、および C++ 標準の不具合の更新) に対するコンパイラおよび標準ライブラリのサポートが無効になります。 これらの機能を有効にするには、 **`/std:c++latest`** を使用します。

### <a name="codegen-security-diagnostics-and-versioning"></a>コード生成、セキュリティ、診断、バージョン管理

このリリースでは、最適化、コード生成、ツールセットのバージョン管理、診断に関して、いくつかの機能強化が行われています。 主な改良点は次のとおりです。

- ループのコード生成の向上: 定数整数の除算の自動ベクター化がサポートされるようになりました。また、memset パターンの識別機能が向上しています。
- コード セキュリティの向上: バッファー オーバーラン コンパイラ診断の出力が向上し、[`/guard:cf`](../build/reference/guard-enable-control-flow-guard.md) によりジャンプ テーブルを生成する switch ステートメントが保護されるようになりました。
- バージョン管理: 組み込みプリプロセッサ マクロ **\_MSC\_VER** の値が、Visual C++ ツールセットの更新のたびに単調に更新されるようになりました。 詳しくは、「[Visual C++ Compiler Version](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/)」(Visual C++ コンパイラのバージョン) をご覧ください。
- 新しいツールセット レイアウト: 開発用コンピューターでのコンパイラおよび関連するビルド ツールの場所とディレクトリ構造が新しくなりました。 新しいレイアウトでは、複数のバージョンのコンパイラのサイド バイ サイド インストールが可能です。 詳細については、「[Compiler Tools Layout in Visual Studio 2017 (Visual Studio 2017 でのコンパイラ ツール レイアウト)](https://devblogs.microsoft.com/cppblog/compiler-tools-layout-in-visual-studio-15/)」をご覧ください。
- 改善された診断機能: 出力ウィンドウにエラーが発生した列が表示されるようになりました。 詳細については、「[C++ compiler diagnostics improvements in VS "15" Preview 5 (VS "15" Preview 5 での C++ コンパイラの診断の機能強化)](https://devblogs.microsoft.com/cppblog/c-compiler-diagnostics-improvements-in-vs-15-rc/)」をご覧ください。
- コルーチンを使用する場合、試験的キーワード **yield** ( **`/await`** オプションによって使用可能) は削除されています。 代わりにコードを書き直し、`co_yield` を使用する必要があります。 詳しくは、「[`yield` keyword to become `co_yield` in VS 2017 (yield キーワードが VS 2017 では co_yield になる)](https://devblogs.microsoft.com/cppblog/yield-keyword-to-become-co_yield-in-vs-2017/)」をご覧ください。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

コンパイラでの診断の機能をさらに強化。 詳細については、「[Diagnostic Improvements in Visual Studio 2017 15.3.0 (Visual Studio 2017 15.3.0 での診断機能の強化)](https://devblogs.microsoft.com/cppblog/diagnostic-improvements-in-vs2017-15-3-0/)」をご覧ください。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

Visual C++ ランタイムの性能が継続的に上がります。生成されたコードの質が良くなるためです。 コードを再コンパイルするだけで、アプリをさらに高速にできます。 コンパイラ最適化の一部はまったく新しい機能です。たとえば、条件付きスカラー ストアをベクター化する、`sin(x)` と `cos(x)` の呼び出しを組み合わせて新しい `sincos(x)` を作る、SSA オプティマイザーから冗長命令を除去するなどです。 その他のコンパイラ最適化は、既存の機能の改善になります。条件式のベクター化ヒューリスティック、ループ最適化の改善、float min/max codegen などです。 リンカーには新しくて速い **`/OPT:ICF`** が実装されました。結果的に、リンク時間が最大 9% スピードアップします。インクリメンタル リンクに他のパフォーマンス修正があります。 詳細については、「[/OPT (最適化)](../build/reference/opt-optimizations.md)」と「[/INCREMENTAL (インクリメンタル リンクを行う)](../build/reference/incremental-link-incrementally.md)」を参照してください。

Microsoft C++ コンパイラは Intel の AVX-512 をサポートしています。 これには、AVX-512 の新しい機能を 128 ビットおよび 256 ビット ワイド レジスタに取り込むベクトル長命令が含まれています。

[`/Zc:noexceptTypes-`](../build/reference/zc-noexcepttypes.md) オプションを利用すれば、全般的に C++17 モードを使用しながら、C++14 バージョンの **`noexcept`** に戻すことができます。 このオプションでソース コードを更新し、C++17 に準拠できます。すべての `throw()` コードを同時に書き直す必要がありません。 詳細については、「[動的例外指定の削除と noexcept](cpp-conformance-improvements-2017.md#noexcept_removal)」を参照してください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

- 予測実行サイドチャネルからの攻撃を緩和する、新しいコンパイラ スイッチの [/Qspectre](../build/reference/qspectre.md)。 詳細については、「[Spectre mitigations in MSVC (MSVC の Spectre 軽減策)](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)」を参照してください。
- Spectre 軽減策用の新しい診断警告。 詳細については、「[Spectre diagnostic in Visual Studio 2017 Version 15.7 Preview 4 (Visual Studio 2017 バージョン 15.7 プレビュー 4 での Spectre 診断)](https://devblogs.microsoft.com/cppblog/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/)」を参照してください。
- /Zc の新しい値 **`/Zc:__cplusplus`** を使用すると、C++ 標準サポートの正しいレポートが可能になります。 たとえば、スイッチが設定され、コンパイラが **`/std:c++17`** モードである場合、値は **`201703L`** に拡張されます。 詳細については、「[MSVC now correctly reports __cplusplus (__cplusplus の MSVC での正しい報告)](https://devblogs.microsoft.com/cppblog/msvc-now-correctly-reports-__cplusplus/)」を参照してください。

## <a name="c-standard-library"></a>C++ 標準ライブラリ

### <a name="correctness-improvements"></a>正確性についての改善

##### <a name="visual-studio-2017-rtm-version-150"></a>Visual Studio 2017 RTM (バージョン 15.0)

- `basic_string``_ITERATOR_DEBUG_LEVEL != 0` の診断は若干改良されました。 IDL チェックが文字列機構でトリップされた場合、トリップの原因となった具体的な動作が報告されるようになりました。 たとえば、"string iterator not dereferencable (文字列反復子を逆参照できません)" の代わりに、"cannot dereference string iterator because it is out of range (e.g. an end iterator) (範囲外のため文字列反復子を逆参照できません (例: 終了反復子))" が報告されます。
- 以前はコードが永続的にブロックされていた `std::promise` の移動代入演算子が修正されました。
- `atomic<T*>` の `T*` への暗黙の変換でコンパイラのエラーが修正されました。
- `pointer_traits<Ptr>` で `Ptr::rebind<U>` が適切に検出されるようになりました。
- `move_iterator` の減算演算子に不足した **`const`** 修飾子が修正されました。
- `propagate_on_container_copy_assignment` および `propagate_on_container_move_assignment` を要求するステートフルなユーザー定義アロケーターのサイレントかつ不適切な codegen が修正されました。
- `atomic<T>` でオーバーロードされた `operator&()` が許容されるようになりました。
- 間違った `bind()` 呼び出しのコンパイラ診断が若干向上しています。

Visual Studio 2017 RTM では、標準ライブラリの機能がさらに強化されています。 完全な一覧については、[VS 2017 RTM の標準ライブラリの修正](https://devblogs.microsoft.com/cppblog/stl-fixes-in-vs-2017-rtm/)に関する C++ チームのブログ エントリを参照してください。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- 標準ライブラリのコンテナーでは、`max_size()` を `size_type` の `max()` ではなく、`numeric_limits<difference_type>::max()` にクランプするようになりました。 この変更により、そのコンテナーからの反復子における `distance()` の結果が、`distance()` の戻り値の型で表現できるようになります。
- 特殊化 `auto_ptr<void>` が欠落する不具合を修正しました。
- `for_each_n()`、`generate_n()`、および `search_n()` アルゴリズムは、length 引数が整数型でない場合、以前はコンパイルに失敗していました。 整数ではない length は、反復子の `difference_type` への変換は試行されるようになりました。
- `normal_distribution<float>` では、double から float への縮小について、標準ライブラリ内で警告を出力しないようになりました。
- 最大サイズのオーバーフローをチェックするときに、`max_size()` ではなく `npos` を使っていた一部の `basic_string` 操作を修正しました。
- 疑似ウェイクが発生した場合、`condition_variable::wait_for(lock, relative_time, predicate)` は相対時間全体にわたって待機していました。 待機時間は、相対時間の 1 つの間隔のみになりました。
- 標準での必要性に応じて、`future::get()` は `future` を無効化するようになりました。
- `iterator_traits<void *>` は `void&` を形成しようとするため、ハード エラーとして使用されていましたが、これが明確に空の構造体となり、"is iterator" SFINAE 条件で `iterator_traits` が使用できるようになりました。
- Clang **-Wsystem-headers** によって報告される警告の一部を修正しました。
- Clang -**Wmicrosoft-exception-spec** によって報告された "宣言での例外指定が以前の宣言と一致しない" 問題も修正しました。
- Clang と C1XX によって報告された mem-initializer-list 順序付けの警告も修正しました。
- 順序なしのコンテナーは、コンテナー自体がスワップされるときにハッシュ関数や述語のスワップを行っていませんでした。 現在は行うようになりました。
- 多くのコンテナー スワップ操作は、マークされた **`noexcept`** となりました (標準ライブラリが non-`propagate_on_container_swap` non-equal-allocator の未定義の動作条件を検出したときに、例外をスローすることがないため)。
- 多くの `vector<bool>` 操作が、マークされた **`noexcept`** になりました。
- 標準ライブラリは、アロケーター `value_type` (C++17 モードで) の照合をオプトアウト エスケープ ハッチで強制するようになりました。
- `basic_string` への self-range-insert が文字列の内容をスクランブルする場合の条件の一部を修正しました。 (注: ベクターへの self-range-insert は、標準によって引き続き禁止されています。)
- `basic_string::shrink_to_fit()` は、アロケーターの `propagate_on_container_swap` によって影響を受けることがなくなりました。
- `std::decay` では、煩雑な関数の型 (cv-qualified、ref-qualified、またはその両方の関数型) が処理されるようになりました。
- include ディレクティブを変更した結果、正しい大文字小文字の区別とスラッシュの使用が可能となり、移植性が向上させました。
- 警告 C4061 "列挙型 '*enumeration*' の switch 文内の列挙子 ’*enumerator*’ は、case ラベルによって明示的に扱われていません" を修正しました。 この警告は既定ではオフになっており、標準ライブラリの警告の全般的なポリシーに対する例外として修正されました。 (標準ライブラリは **`/W4`** クリーンですが、 **`/Wall`** クリーンにしようとはしません。 既定でオフである警告の多くは、非常にノイズが多く、日常的に使用するためのものではありません)。
- `std::list` のデバッグ チェックが強化されました。 リストの反復子は `operator->()` をチェックし、`list::unique()` では反復子を無効としてマークするようになりました。
- `tuple` 内の uses-allocator メタプログラミングを修正しました。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- `std::partition` は標準で要求される `N + 1` 回ではなく、`N` 回述語を呼び出すようになりました。
- バージョン 15.3 で見られた、静的マジックを回避する試みがバージョン 15.5 で修正されました。
- `std::atomic<T>` では、既定で構造化可能になることが `T` に要求されなくなりました。
- 対数時間を要するヒープ アルゴリズムは、反復子のデバッグが有効な場合、異なる動作になります。 入力が実際にヒープであるという線形の時間アサーションは実行されなくなりました。
- `__declspec(allocator)` は今後、C1XX の場合のみ、この declspec を理解しない Clang からの警告を防ぐ目的で保護されます。
- `basic_string::npos` は今後、コンパイル時間定数として利用できます。
- `std::allocator` は C++17 モードで、アラインメントが `max_align_t` を超える、オーバーアラインされている型の割り当てを適切に処理するようになりました ( **`/Zc:alignedNew-`** によって無効にされていない限り)。  たとえば、SSE および AVX 命令で、アラインメントが 16 バイトまたは 32 バイトのオブジェクトのベクトルが正しく調整されるようになりました。

### <a name="conformance-improvements"></a>準拠の強化

- \<any\>、\<string_view\>、`apply()`、`make_from_tuple()` を追加しました。
- \<optional\>、\<variant\>、`shared_ptr::weak_type`、\<cstdalign\> を追加しました。
- `min(initializer_list)`、`max(initializer_list)`、`minmax(initializer_list)`、`min_element()`、`max_element()`、`minmax_element()` で、C++14 の **`constexpr`** が有効になりました。

詳細については、「[Microsoft C++ 言語の準拠表](./visual-cpp-language-conformance.md)」を参照してください。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- C++17 の追加機能がいくつか実装されました。 詳細については、「[Microsoft C++ 言語の準拠表](cpp-conformance-improvements-2017.md#improvements_153)」を参照してください。
- P0602R0 "variant と optional は自明的にコピー/移動を伝達する必要がある" を実装しました。
- 標準ライブラリでは、[/GR-](../build/reference/gr-enable-run-time-type-information.md) オプションで無効にされた動的 RTTI が正式に許容されるようになりました。 `dynamic_pointer_cast()` と `rethrow_if_nested()` には本質的に **`dynamic_cast`** が必要なため、標準ライブラリでは **`/GR-`** の指定時にこれらの関数が `=delete` としてマークされるようになりました。
- 動的 RTTI が **`/GR-`** で無効にされた場合でも、`typeid(SomeType)` の形式の "static RTTI" は引き続き使用可能で、標準ライブラリの一部のコンポーネントを強化します。 標準ライブラリでは、 **`/D_HAS_STATIC_RTTI=0`** でこの機能の無効化もサポートされるようになりました。 このフラグでは、`std::any`、`std::function` の `target()` および `target_type()` メンバー関数、さらに `std::shared_ptr` および `std::weak_ptr` の `get_deleter()` フレンド メンバー関数も無効になることに注意してください。
- 標準ライブラリでは、条件付きで定義されたマクロではなく、無条件で C++14 **`constexpr`** が使用されるようになりました。
- 標準ライブラリでは、エイリアス テンプレートを内部で使用するようになりました。
- 標準ライブラリでは、`nullptr_t{}` ではなく、 **`nullptr`** が内部で使用されるようになりました。 (NULL は内部で使用できなくなりました。 0 を null として内部で使用している箇所は、徐々に削除されています。)
- 標準ライブラリでは、様式上 `std::forward()` を誤用するのではなく、`std::move()` を内部で使用するようになりました。
- `static_assert(false, "message")` を `#error message` に変更しました。 この変更により、`#error` でコンパイルが即時中止されるため、コンパイラによる診断が向上します。
- 標準ライブラリでは、関数を `__declspec(dllimport)` としてマークしなくなりました。 最新のリンカー テクノロジでは、それが不要になりました。
- SFINAE を既定のテンプレート引数に抽出するため、戻り値型と関数引数型に比べて、煩雑さが軽減されました。
- \<random\> のデバッグ チェックでは、`fputs()` を **stderr** に呼び出す内部関数 `_Rng_abort()` ではなく、標準ライブラリの通常のメカニズムが使用されるようになりました。 この関数の実装は、バイナリの互換性のために保持されています。 標準ライブラリの次のバイナリ互換性のないバージョンでは、このファイルを削除する予定です。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- C++ 17 標準に従って、いくつかの標準ライブラリ機能の追加、非推奨化、または削除が行われました。 詳細については、「[Visual Studio の C++ 準拠の強化](cpp-conformance-improvements-2017.md#improvements_155)」をご覧ください。
- 次の並列アルゴリズムが試験的にサポートされます。
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- 次の並列アルゴリズムの署名が追加されましたが、現時点では並列化されていません。 要素を移動または並べ替えるだけのアルゴリズムを並列化する場合、プロファイリングには利点がありませんでした。
  - `copy`
  - `copy_n`
  - `fill`
  - `fill_n`
  - `move`
  - `reverse`
  - `reverse_copy`
  - `rotate`
  - `rotate_copy`
  - `swap_ranges`

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 バージョン 15.6

- \<memory_resource>
- ライブラリ基礎 V1
- `polymorphic_allocator` の割り当ての削除
- クラス テンプレート引数の推論の機能強化

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

- 並列アルゴリズムのサポートが試験段階ではなくなった
- \<filesystem> の新しい実装
- 基本文字列変換 (部分的)
- `std::launder()`
- `std::byte`
- `hypot(x,y,z)`
- 不要な decay の回避
- 数学的特殊関数
- `constexpr char_traits`
- 標準ライブラリの推論ガイド

詳細については、「[Microsoft C++ 言語の準拠表](./visual-cpp-language-conformance.md)」を参照してください。

### <a name="performance-and-throughput-fixes"></a>パフォーマンスやスループットの修正

- `basic_string::find(char)` オーバーロードで `traits::find` が 1 回だけ呼び出されるようになりました。 これまでは、長さ 1 の文字列の一般的な文字列検索として実装されていました。
- `basic_string::operator==` では、文字列の内容を比較する前に文字列のサイズがチェックされるようになりました。
- コンパイラ オプティマイザーによる分析が困難であった `basic_string` でのコントロールの結合が削除されました。 短い文字列では、`reserve` を呼び出すと、処理は何も行われませんがコストは 0 ではありません。
- `std::vector` が正確性とパフォーマンスについて徹底的に見直されました。挿入および配置操作中のエイリアシングが標準に従って適切に処理されるようになりました。強固な例外保証が、標準で求められるときに `move_if_noexcept()` およびその他のロジックを介して提供されるようになりました。挿入および配置に伴う要素の操作が少なくなりました。
- C++ 標準ライブラリでは、手の込んだ null ポインターの逆参照が回避されるようになりました。
- `weak_ptr::lock()` パフォーマンスが向上しました。
- コンパイラのスループットを上げるため、C++ 標準ライブラリ ヘッダーで不要なコンパイラ組み込みの宣言を含むことが回避されるようになりました。
- `std::string` および `std::wstring` の移動コンストラクターのパフォーマンスが 3 倍以上に向上しました。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- 構造化例外処理 (SEH) を使用する関数に `std::atomic` の実装をインライン展開することを妨げる、 **`noexcept`** との相互作用が回避されました。
- 標準ライブラリの `_Deallocate()` 内部関数を変更してより小さなコードに最適化し、より多くの場所にインライン化できるようにしました。
- `std::try_lock()` を変更し、再帰の代わりにパック展開を使用するようにしました。
- `std::lock()` のデッドロック回避アルゴリズムを改善し、すべてのロックで `try_lock()` を使用するのではなく、`lock()` 操作を使用するようにしました。
- `system_category::message()` で名前付きの戻り値の最適化を有効にしました。
- `conjunction` と `disjunction` では、`2N + 2` 型ではなく、`N + 1` 型がインスタンス化されるようになりました。
- `std::function` が各々の型消去呼び出しのアロケーター サポート メカニズムをインスタンス化しなくなり、多くの異なるラムダを `std::function` に渡すプログラムでスループットが向上し、.obj サイズが縮小しました。
- `allocator_traits<std::allocator>` に手動でインライン化された `std::allocator` 操作が含まれたことにより、`allocator_traits` のみで `std::allocator` とやり取りするコード (つまりほとんどのコード) のコード サイズが縮小されます。
- C++ 11 の最小アロケーター インターフェイスは、内部クラス `_Wrap_alloc` 内のアロケーターをラップするのでなく、直接 `allocator_traits` を呼び出す標準ライブラリによって処理されるようになりました。 この変更により、アロケーター サポートに対して生成されるコード サイズが小さくなり、オプティマイザーの機能が向上して標準ライブラリのコンテナーを推測できる場合があり、デバッグ エクスペリエンスが向上します (デバッガーで `_Wrap_alloc<your_allocator_type>` ではなくアロケーター型を表示するようになりました)。
- カスタマイズされた `allocator::reference` のメタプログラミングを削除しました。これは、アロケーターをカスタマイズすることは許可されていないものです (アロケーターは、コンテナーが手の込んだポインターを使用するようにできますが、手の込んだ参照を使用するようにはできません。)
- コンパイラのフロントエンドが、範囲ベースの for ループでデバッグ反復子のラップを解除するようにしてあり、デバッグ ビルドのパフォーマンスを向上させます。
- `shrink_to_fit()` と `reserve()` への `basic_string` の内部圧縮パスは再割り当て操作のパスではなくなったため、変化を伴うすべてのメンバーのコード サイズが減少します。
- `basic_string` の内部拡張パスが、`shrink_to_fit()` のパスからなくなりました。
- `basic_string` の変更操作が、非割り当て高速パスと割り当て低速パスの関数に含まれるようになり、一般的な非割り当てのケースが呼び出し元にインライン化されやすくなりました。
- `basic_string` の変化を伴う操作が、インプレースでサイズ変更するのではなく、目的の状態で、再割り当てバッファーを構築するようになりました。 たとえば、文字列の先頭に挿入すると、挿入後にコンテンツが 1 回だけ移動されるようになりました。 下に移動されるか、新しく割り当てられたバッファーに移動されます。 再割り当ての場合、最初に新しく割り当てられたバッファーに移動されてから下に移動されることはなくなりました。
- \<string\> 内の C 標準ライブラリを呼び出す操作では、`errno` のアドレスをキャッシュに格納することで、TLS でのやり取りを繰り返さないようになりました。
- `is_pointer` の実装を簡素化しました。
- 関数ベースの SFINAE 式から **`struct`** および `void_t` ベースへの変更が完了しました。
- 標準ライブラリのアルゴリズムで、ポスト インクリメントの反復子を使用しないようになりました。
- 64 ビット システムで 32 ビットのアロケーターを使用した場合の切り捨ての警告を修正しました。
- non-POCMA non-equal-allocator の場合に、バッファーが使用可能な場合は再利用することによって、`std::vector` 移動割り当てがより効率的になるようになりました。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- `basic_string<char16_t>` は、`basic_string<wchar_t>` が連動するのと同じ `memcmp`、`memcpy`、および類似の最適化と連動するようになりました。
- オプティマイザーに制約があり、Visual Studio 2015 更新プログラム 3 の "関数のコピーを避ける" で関数ポインターがインライン公開されることが妨げられていましたが、それが回避されました。`lower_bound(iter, iter, function pointer)` のパフォーマンスが元に戻ります。
- 反復子デバッグで、`includes`、`set_difference`、`set_symmetric_difference`、`set_union` への入力の順序を検証するためのオーバーヘッドは、順序の確認前に反復子の折り返しを解除することで減らされました。
- `std::inplace_merge` は、既に定位置にある要素をスキップするようになりました。
- `std::random_device` の構築では、`std::string` を構築し、その後破棄することがなくなりました。
- `std::equal` と `std::partition` でジャンプスレッドという最適化に成功しました。この最適化で反復子比較が省かれます。
- `std::reverse` に普通にコピー可能な `T` のポインターが渡されると、手書きのベクター化された実装にディスパッチします。
- `std::fill`、`std::equal`、`std::lexicographical_compare` は、`std::byte` と `gsl::byte` (さらに、その他の char などの列挙型と enum クラス) の `memset` および `memcmp` にディスパッチする方法を学習しました。 `std::copy` では `is_trivially_copyable` を使ってディスパッチするので、いかなる変更も必要ありませんでした。
- 標準ライブラリにはもう、唯一の行動が型を non-trivially-destructible (普通に破棄できない) にすることであった空のかっこのデストラクターが含まれていません。

## <a name="other-libraries"></a>他のライブラリ

### <a name="open-source-library-support"></a>オープンソース ライブラリのサポート

**Vcpkg** は、Visual Studio でオープンソースの C++ スタティック ライブラリと DLL を取得してビルドするプロセスを大幅に単純化するオープンソースのコマンド ライン ツールです。 詳細については、[vcpkg: C++ 用のパッケージ マネージャー](../build/vcpkg.md)に関する記事を参照してください。

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

C++ 用のクロスプラットフォーム Web API である CPPRestSDK が、バージョン 2.9.0 に更新されました。 詳しくは、「[CppRestSDK 2.9.0 is available on GitHub](https://devblogs.microsoft.com/cppblog/cpprestsdk-2-9-0-is-available-on-github/)」(CppRestSDK 2.9.0 が GitHub で入手可能) をご覧ください。

### <a name="atl"></a>ATL

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- もう 1 つの名前検索の適合性が解決しました
- 既存の移動コンストラクターと移動代入演算子が非スローとして正しくマークされるようになりました。
- atlstr.h のローカルな静的変数のスレッド セーフな init に関する有効な警告 (C4640) の抑制が解除されました。
- ATL を使って DLL をビルドするとき、XP ツールセットで、ローカルな静的変数のスレッドセーフな初期化が自動的に無効になっていました。 現在ではそうではなくなりました。 スレッドセーフな初期化が必要ない場合は、プロジェクト設定に **`/Zc:threadSafeInit-`** を追加できます。

### <a name="visual-c-runtime"></a>Visual C++ ランタイム

- コントロール フロー ガード シンボルに新しいヘッダー "cfguard.h" が追加されました。

## <a name="visual-studio-2017-c-ide"></a>Visual Studio 2017 C++ IDE

- C++ ネイティブ プロジェクトの構成変更が簡単になりました。C++/CLI プロジェクトの場合、さらに簡単です。 ソリューション構成を初めて有効にするとき、そのプロセスが以前より速やかに進行し、そのソリューション構成の後続のアクティベーションがすべて即座に完了します。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- プロジェクトとコードのいくつかのウィザードを署名ダイアログのスタイルで書き直しました。
- **[クラスの追加]** でクラス追加ウィザードが直接起動されるようになりました。 以前ここにあったその他の項目はすべて、 **[追加] > [新しい項目]** に移動しています。
- **[新しいプロジェクト]** ダイアログで、Win32 プロジェクトが **[Windows デスクトップ]** カテゴリに表示されるようになりました。
- **Windows コンソール** のテンプレートと **Windows デスクトップ アプリケーション** のテンプレートで、ウィザードなしでプロジェクトを作成するようになりました。 以前の **Win32 コンソール アプリケーション** ウィザードと同じオプションを表示する同じカテゴリに新しい **Windows デスクトップ ウィザード** が追加されました。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

リファクタリングとコード ナビゲーションに IntelliSense エンジンを使用する C++ 演算のいくつかがより速く実行されます。 次の数値は Visual Studio Chromium ソリューションと 3500 件のプロジェクトに基づきます。

| 機能 | パフォーマンス改善 |
|--|--|
| 名前の変更 | 5.3x |
| シグネチャの変更 | 4.5x |
| [すべての参照の検索] | 4.7x |

C++ では、Ctrl を押しながら **[定義へ移動]** をクリックできるようになりました。マウス操作で簡単に定義に移動できます。 Productivity Power Tools パックの構造ビジュアライザーが既定で製品にも含まれるようになりました。

## <a name="intellisense"></a>IntelliSense

- SQLite ベースの新しいデータベース エンジンが、既定で使用されるようになりました。 新しいエンジンでは、 **[定義へ移動]** や **[すべての参照を検索]** などのデータベース操作が高速になりました。 これにより、ソリューションの初期解析時間が大幅に向上します。 設定は、 **[ツール] > [オプション] > [テキスト エディター] > [C/C++] > [詳細]** に移動されました (以前は ... [C/C++] > [実験用] にありました)。

- プリコンパイル済みヘッダーを使用していないプロジェクトやファイルでの IntelliSense のパフォーマンスが向上しました。現在のファイルのヘッダーに対して自動プリコンパイル済みヘッダーが作成されます。

- エラー一覧の IntelliSense エラーに対するフィルター処理とヘルプが追加されました。 エラー列をクリックするとフィルター処理を実行できます。 また、特定のエラーをクリックするか F1 キーを押すと、エラー メッセージのオンライン検索が開始します。

  ![エラー一覧](media/ErrorList1.png "エラー一覧")

  ![フィルター処理されたエラー一覧](media/ErrorList2.png "フィルター処理されたエラー一覧")

- メンバー リストの項目を種類別にフィルターする機能が追加されました。

  ![メンバー一覧のフィルター処理](media/mlfiltering.png "メンバー リストのフィルター処理")

- メンバー リストの表示項目のコンテキストに応じたフィルター処理を提供する新しい実験的な予測 IntelliSense 機能が追加されました。 詳しくは、「[C++ IntelliSense Improvements - Predictive IntelliSense & Filtering (C++ IntelliSense の機能改善 - 予測 IntelliSense とフィルター処理)](https://devblogs.microsoft.com/cppblog/c-intellisense-improvements-predictive-intellisense-filtering/)」を参照してください。
- **[すべての参照の検索]** (Shift + F12) を使って、複雑なコードベースでも簡単に参照できるようになりました。 高度なグループ化、フィルター処理、並べ替え、結果内の検索と色づけ (一部の言語) が提供され、参照を明確に理解できます。 C++ では、新しい UI に、変数から読み取っているのか、または変数に書き込んでいるのかに関する情報が含まれます。
- Dot-to-Arrow IntelliSense 機能が試験段階から進んだ段階に移り、既定で有効になっています。 エディターの **[Expand Scopes]\(スコープの展開\)** および **[Expand Precedence]\(優先順位の展開\)** 機能が試験段階から進んだ段階に移ります。
- 試験的なリファクタリング機能である **署名の変更** および **関数の抽出** が既定で使用可能になりました。
- C++ プロジェクトの "迅速なプロジェクトの読み込み" の試験的機能が追加されました。 C++ プロジェクトを次回に開いた際に、読み込みが速くなり、またそれ以降、読み込みが "*さらに*" 速くなります。
- 他の言語と共通の機能と、C++ に固有の機能があります。 これらの新機能について詳しくは、「[Announcing Visual Studio "15" Preview 5 (Visual Studio "15" プレビュー 5 のご案内)](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-15-preview-5/)」をご覧ください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

- ClangFormat のサポートが追加されました。 詳細については、「[ClangFormat Support in Visual Studio 2017](https://devblogs.microsoft.com/cppblog/clangformat-support-in-visual-studio-2017-15-7-preview-1/)」 (Visual Studio 2017 での ClangFormat のサポート) を参照してください。

## <a name="non-msbuild-projects-with-open-folder"></a>非 MSBuild プロジェクトと [フォルダーを開く]

Visual Studio 2017 では、 **[フォルダーを開く]** 機能が導入されました。 ソリューションやプロジェクトを作成することなく、ソース コードが格納されているフォルダーでコーディング、ビルド、デバッグを行うことができます。 現在は、プロジェクトが MSBuild ベースではない場合でも、Visual Studio を簡単に使い始めることができます。 **[フォルダーを開く]** を使用すると、強力なコードの理解機能、編集機能、構築機能、デバッグ機能にアクセスできます。 これらは、Visual Studio で MSBuild プロジェクト用に既に提供されているものと同じです。 詳細については、「[Open Folder projects for C++](../build/open-folder-projects-cpp.md)」 (C++ の [フォルダーを開く] プロジェクト) をご覧ください。

- [フォルダーを開く] のエクスペリエンスが改善されました。 以下の json ファイルを使って、エクスペリエンスをカスタマイズできます。
  - CppProperties.json: IntelliSense および参照エクスペリエンスをカスタマイズします。
  - Tasks.json: ビルド ステップをカスタマイズします。
  - Launch.json: デバッグ エクスペリエンスをカスタマイズします。

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- MinGW や Cygwin といった、別のコンパイラとビルド環境のサポートを強化しました。 詳細については、「[Using MinGW and Cygwin with Visual C++ and Open Folder (Visual C++ と [フォルダーを開く] で MinGW と Cygwin を使用する)](https://devblogs.microsoft.com/cppblog/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/)」をご覧ください。
- CppProperties.json と CMakeSettings.json でグローバル環境変数と構成固有の環境変数を定義するためのサポートが追加されました。 この環境変数は、launch.vs.json に定義されているデバッグ構成と tasks.vs.json のタスクで利用されます。 詳細については、「[Customizing your Environment with Visual C++ and Open Folder](https://devblogs.microsoft.com/cppblog/customizing-your-environment-with-visual-c-and-open-folder/)」 (Visual C++ と [フォルダーを開く] で環境をカスタマイズする) をご覧ください。
- 簡単に 64 ビット プラットフォームを対象とする機能など、CMake の Ninja generator のサポートを強化しました。

## <a name="cmake-support-via-open-folder"></a>[フォルダーを開く] での CMake のサポート

Visual Studio 2017 では、MSBuild プロジェクト ファイル (.vcxproj) を変換しなくても、CMake プロジェクトを使用できるようになりました。 詳細については、「[CMake projects in Visual Studio](../build/cmake-projects-in-visual-studio.md)」 (Visual Studio の CMake プロジェクト) をご覧ください。 **[フォルダーを開く]** で CMake プロジェクトを開くと、C++ の編集、ビルド、およびデバッグ用の環境が自動的に構成されます。

- C++ の IntelliSense は、ルート フォルダーに CppProperties.json ファイルを作成しなくても動作します。 また、CMake に用意された構成と CppProperties.json ファイルをユーザーが簡単に切り替えることができるように新しいドロップダウンが追加されました。

- CMakeLists.txt ファイルと同じフォルダーに配置される CMakeSettings.json ファイルにより、追加の構成がサポートされます。

  ![CMake の [フォルダーを開く]](media/cmake-cpp.png "CMake の [フォルダーを開く]")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- CMake Ninja generator のサポートが追加されました。

##### <a name="visual-studio-2017-version-154"></a>Visual Studio 2017 バージョン 15.4

- 既存の CMake キャッシュをインポートするためのサポートが追加されました。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- CMake 3.11、CMake プロジェクトでのコード分析、ソリューション エクスプローラーのターゲット ビュー、キャッシュ生成用のオプション、および単一ファイルのコンパイルのためのサポートが追加されました。 詳細については、[Visual Studio での CMake のサポート](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/)に関するページと、「[Visual Studio の CMake プロジェクト](../build/cmake-projects-in-visual-studio.md)」をご覧ください。

## <a name="windows-desktop-development"></a>Windows デスクトップ開発

元の C++ ワークロードのインストールに対して、より詳細なインストール エクスペリエンスを提供します。 必要なツールだけをインストールできる選択可能なコンポーネントが追加されました。 インストーラーの UI のコンポーネント一覧で示されるインストール サイズは正確ではなく、合計サイズが少なめに表示されます。

C++ デスクトップ ワークロードで Win32 プロジェクトを作成するには、ツールセットと Windows SDK の両方をインストールする必要があります。 推奨される (選択されている) コンポーネント **VC++ 2017 v141 toolset (x86, x64)** と **Windows 10 SDK (10.0.nnnnn)** をインストールすれば、確実に実行できます。 必要なツールがインストールされていない場合、プロジェクトは正常に作成されず、ウィザードが応答を停止します。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

Visual C++ Build ツール (以前はスタンドアロン製品として入手できた) は現在、Visual Studio インストーラーにワークロードとして含まれています。 このワークロードは、C++ プロジェクトの構築に必要なツールだけをインストールします。Visual Studio IDE はインストールしません。 v140 と v141 のいずれのツールセットも含まれます。 v141 ツールセットには Visual Studio 2017 バージョン 15.5 の最新の機能強化が含まれています。 詳細については、「[Visual Studio Build Tools now include the VS2017 and VS2015 MSVC Toolsets](https://devblogs.microsoft.com/cppblog/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)」 (Visual Studio Build Tools に VS2017 および VS2015 MSVC ツールセットが追加されました) を参照してください。

## <a name="linux-development-with-c"></a>C++ による Linux 開発

よく利用される拡張機能である [Visual C++ for Linux Development](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.VisualCforLinuxDevelopment) が Visual Studio に組み込まれます。 このインストールでは、Linux 環境で実行する C++ アプリケーションの開発とデバッグに必要なすべてのものが提供されます。

##### <a name="visual-studio-2017-version-152"></a>Visual Studio 2017 バージョン 15.2

クロスプラットフォームのコード共有と型の視覚化の機能強化が行われました。 詳細については、「[Linux C++ improvements for cross-platform code sharing and type visualization (Linux C++ の、クロスプラットフォームのコード共有と型の視覚化の機能強化)](https://devblogs.microsoft.com/cppblog/linux-cross-platform-and-type-visualization/)」をご覧ください。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- Linux ワークロードでは、リモート Linux マシンにファイルを同期するための **sftp** の代替として **rsync** が使えるようになりました。
- ARM マイクロコントローラーを対象とするクロス コンパイルのサポートが追加されました。 インストールでそれを有効にするには、**C++ による Linux 開発** ワークロードを選び、**埋め込みおよび IoT 開発** のオプションを選びます。 このオプションでは、ARM GCC クロス コンパイル ツールと Make がインストールに追加されます。 詳細については、「[ARM GCC Cross Compilation in Visual Studio](https://devblogs.microsoft.com/cppblog/arm-gcc-cross-compilation-in-visual-studio/)」 (Visual Studio の ARM GCC クロス コンパイル) を参照してください。
- CMake のサポートが追加されました。 Visual Studio プロジェクトに変換しなくても、既存の CMake コード ベースで作業できるようになりました。 詳細については、「[Configure a Linux CMake Project](../linux/cmake-linux-project.md)」 (Linux CMake プロジェクトを構成する) を参照してください。
- リモート タスクを実行するためのサポートが追加されました。 この機能により、Visual Studio の接続マネージャーに定義されているリモート システムであらゆるコマンドを実行できます。 リモート タスクでは、リモート システムにファイルをコピーすることもできます。
詳細については、「[Configure a Linux CMake Project](../linux/cmake-linux-project.md)」 (Linux CMake プロジェクトを構成する) を参照してください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

- Linux ワークロードのシナリオへのさまざまな機能強化。 詳細については、「[Linux C++ Workload improvements to the Project System, Linux Console Window, rsync and Attach to Process](https://devblogs.microsoft.com/cppblog/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/)」(プロジェクト システム、Linux コンソール ウィンドウ、rsync およびプロセスへのアタッチに対する Linux C++ ワークロードの機能改善) を参照してください。
- リモート Linux 接続のヘッダーでの IntelliSense。 詳細については、「[IntelliSense for Remote Linux Headers](https://devblogs.microsoft.com/cppblog/intellisense-for-remote-linux-headers/)」 (リモート Linux ヘッダーでの IntelliSense) および「[Linux CMake プロジェクトを構成する](../linux/cmake-linux-project.md)」を参照してください。

## <a name="game-development-with-c"></a>C++ によるゲーム開発

C++ を最大限に活用して DirectX または Cocos2d で駆動するプロフェッショナルなゲームを構築します。

## <a name="mobile-development-with-c-for-android-and-ios"></a>C++ による Android および iOS 用のモバイル開発

Android および iOS を対象とするモバイル アプリを、Visual Studio を使用して作成およびデバッグできるようになりました。

## <a name="universal-windows-apps"></a>ユニバーサル Windows アプリ

ユニバーサル Windows アプリ ワークロードのオプション コンポーネントとして、C++ が提供されます。 現在は、C++ プロジェクトを手動でアップグレードする必要があります。 Visual Studio 2017 では、v140 をターゲットとしたユニバーサル Windows プラットフォーム プロジェクトを開くことができます。 ただし、Visual Studio 2015 がインストールされていない場合は、プロジェクトのプロパティ ページで v141 プラットフォームのツールセットを選択する必要があります。

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>ユニバーサル Windows プラットフォーム (UWP) での C++ の新しいオプション

ユニバーサル Windows プラットフォームおよび Windows ストア用の C++ アプリケーションを記述およびパッケージ化するための新しいオプションが追加されました。デスクトップ ブリッジ インフラストラクチャを使用すると、既存のデスクトップ アプリケーションまたは COM オブジェクトをパッケージ化して、Windows ストアを介して配置することができます。 または、サイドローディングを使用して既存のチャネルを介して配置することができます。 Windows 10 の新機能を使用すると、さまざまな方法で、デスクトップ アプリケーションに UWP 機能を追加できます。 詳細については、[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

**Windows アプリケーション パッケージ プロジェクト** というプロジェクト テンプレートが追加されました。このテンプレートでは、デスクトップ ブリッジでのデスクトップ アプリケーションのパッケージ化が大幅に簡略化されます。 **[ファイル] > [新規] > [プロジェクト] > [インストール] > [Visual C++] > [ユニバーサル Windows プラットフォーム]** の下にあります。 詳細については、「[Visual Studio を使ったアプリのパッケージ化 (デスクトップ ブリッジ)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)」をご覧ください。

新しいコードを作成するときに、ヘッダー ファイルだけに実装される Windows ランタイム向けの標準 C++ 言語プロジェクションである C++/WinRT を使うことができるようになりました。 標準に準拠した C++ コンパイラを使用して、Windows ランタイム API を使用および作成できます。 C++/WinRT は、C++ の開発者が最新の Windows API に最適にアクセスできるように設計されています。 詳細については、「[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/)」を参照してください。

Windows SDK Insider プレビューのビルド 17025 以降、C++/WinRT が Windows SDK に含まれるようになりました。 詳細については、「[C++/WinRT is now included the Windows SDK](https://devblogs.microsoft.com/cppblog/cppwinrt-is-now-included-the-windows-sdk/)」 (C++/WinRT が Windows SDK に追加されました) を参照してください。

## <a name="the-clangc2-platform-toolset"></a>Clang/C2 プラットフォーム ツールセット

Visual Studio 2017 に同梱されている Clang/C2 ツールセットが **`/bigobj`** スイッチをサポートするようになりました。これは、大規模なプロジェクトを構築する際に重要です。 また、コンパイラのフロントエンドとバックエンドの両方について、いくつかの重要なバグ修正が組み込まれました。

## <a name="c-code-analysis"></a>C++ コードの分析

[C++ コア ガイドライン](https://github.com/isocpp/CppCoreGuidelines)を適用するための C++ コア チェッカーが Visual Studio で配布されています。 チェッカーは、プロジェクトのプロパティ ページの **[Code Analysis Extensions]\(コード分析の拡張機能\)** ページで有効にしてください。 拡張機能は、コード分析を実行するときに含まれます。 詳細については、「[Using the C++ Core Guidelines checkers (C++ Core ガイドラインのチェッカーを使用する)](../code-quality/using-the-cpp-core-guidelines-checkers.md)」をご覧ください。

![[構成プロパティ] > [コード分析] > [全般] が選択され、[この規則セットを実行] セクションにいくつかの Core Checks が一覧表示されている [プロパティ ページ] ダイアログ ボックスのスクリーンショット。](media/CppCoreCheck.png "CppCoreCheck のプロパティ ページ")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 バージョン 15.3

- リソース管理に関連するルールのサポートが追加されました。

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

- 新しい C++ Core Guidelines チェックでは、スマート ポインターが正しいこと、グローバル初期化子の使い方が正しいこと、コンストラクトのフラグ使用 ( **`goto`** や不良キャストなど) が確認されます。

- 15.3 で使われていた警告番号の一部は 15.5 では使われなくなりました。 より具体的なチェックに置換されました。

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 バージョン 15.6

- 単一ファイルの分析、および分析実行時のパフォーマンス向上のサポートの追加。 詳細については、「[C++ Static Analysis Improvements for Visual Studio 2017 15.6 Preview 2](https://devblogs.microsoft.com/cppblog/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)」 (Visual Studio 2017 15.6 プレビュー 2 での C++ スタティック分析の改善) を参照してください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

- 実行するコード分析ルールを指定できる [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) のサポートの追加。
- 追加の C++ Core Guidelines ルールのサポートの追加。  詳細については、「[Using the C++ Core Guidelines checkers (C++ Core ガイドラインのチェッカーを使用する)](../code-quality/using-the-cpp-core-guidelines-checkers.md)」をご覧ください。

## <a name="unit-testing-in-visual-studio-2017"></a>Visual Studio 2017 での単体テスト

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 バージョン 15.5

**[C++ によるデスクトップ開発]** ワークロードのコンポーネントとして、Google Test Adapter と Boost.Test Adapter を使用できるようになりました。 これらは **テスト エクスプローラー** と統合されています。 CMake プロジェクト ([フォルダーを開く] を使用) のための CTest サポートが追加されました。ただし、**テスト エクスプローラー** との完全統合はまだ利用できません。 詳細については、「[C/C++ 用の単体テストの記述](/visualstudio/test/writing-unit-tests-for-c-cpp)」を参照してください。

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 バージョン 15.6

- `Boost.Test` ダイナミック ライブラリ サポートのサポートが追加されました。
- `Boost.Test` 項目テンプレートが IDE で使用できるようになりました。

詳細については、「[`Boost.Test` Unit Testing: Dynamic Library support and New Item Template](https://devblogs.microsoft.com/cppblog/boost-test-unit-testing-dynamic-library-support-and-new-item-template/)」(Boost.Test 単体テスト: 動的ライブラリのサポートと新しい項目テンプレート) を参照してください。

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 バージョン 15.7

C++ 単体テスト プロジェクトへの [CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) のサポートの追加。 詳細については、「[Announcing CodeLens for C++ Unit Testing](https://devblogs.microsoft.com/cppblog/announcing-codelens-for-c-unit-testing/)」 (C++ 単体テスト用の CodeLens の発表) を参照してください。

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio グラフィックス診断

Visual Studio グラフィックス診断ツール:これらを使用して、Direct3D アプリのレンダリングとパフォーマンスの問題を記録および分析できます。 Windows PC、Windows デバイス エミュレーター、またはリモート PC またはデバイスのローカルで実行されるアプリに対して使用します。

- **頂点シェーダーとジオメトリ シェーダーの入力と出力:** 頂点シェーダーとジオメトリ シェーダーの入力と出力を表示する機能は、リクエストが最も多い機能の 1 つでした。 これはツールでサポートされるようになりました。 パイプライン ステージ ビューで VS または GS ステージを選択すると、次の表の入力と出力を調べることができます。

  ![シェーダーの入力/出力](media/io-shaders.png)

- **オブジェクト テーブルでの検索とフィルター:** 探しているリソースを検索する迅速かつ簡単な手段を提供します。

  ![[種類] ドロップダウンと [検索] テキスト ボックスが強調された [オブジェクト テーブル] セクションのスクリーンショット。](media/search.png)

- **リソース履歴:** この新しいビューは、キャプチャされたフレームのレンダリング時に使われたリソースの全体の変更履歴を表示する簡単な手段を提供します。 リソースの履歴を呼び出すには、リソースのハイパーリンクの横にある時計のアイコンをクリックします。

  ![リソース履歴](media/resource-history.png)

  新しい **リソース履歴** ツール ウィンドウに、リソースの変更履歴が表示されます。

  ![リソース履歴の変更](media/resource-history-change.png)

  完全な呼び出し履歴のキャプチャを有効にしてフレームをキャプチャできます。 これにより、各変更イベントのコンテキストを簡単に推測し、Visual Studio プロジェクト内でそれを調べることができます。 Visual Studio の **[ツール] > [オプション]** ダイアログの **[グラフィックス診断]** で完全なスタックのキャプチャ オプションを設定します。

- **API 統計情報:** フレームでの API の使用の概要を表示します。 自分で行っていることにまったく気付いていない呼び出し、または多すぎる呼び出しを発見するのに便利です。 このウィンドウは、Visual Studio Graphics Analyzer の **[表示] > [API 統計情報]** から表示できます。

  ![API 統計情報](media/api-stats.png)

- **メモリ統計情報:** フレームで作成されたリソースにドライバーが割り当てているメモリの量を表示します。 このウィンドウは、**Visual Studio Graphics Analyzer** の **[表示]、[メモリ統計情報]** から表示できます。 スプレッドシートで表示するためにデータを CSV ファイルにコピーするには、右クリックして **[すべてコピー]** を選択します。

  ![メモリ統計情報](media/memory-stats.png)

- **フレームの検証:** 新しいエラーと警告の一覧は、Direct3D デバッグ レイヤーで検出された潜在的な問題を基に、イベント リストを移動する簡単な方法を提供します。 ウィンドウを開くには、Visual Studio Graphics Analyzer で **[表示]、[フレームの検証]** をクリックします。 次に、 **[検証の実行]** をクリックして分析を開始します。 フレームの複雑さによっては、完了するまでに数分かかることがあります。

  ![フレームの検証](media/frame-validation.png)

- **D3D12 のフレーム分析:** フレーム分析を使って、指示された "what-if" 実験で描画呼び出しのパフォーマンスを分析します。 [フレーム分析] タブに切り替え、分析を実行してレポートを表示します。 詳細については、「[GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool)」(GoingNative 25: Visual Studio のグラフィックス フレーム分析) のビデオをご覧ください。

  ![フレーム分析](media/frame-analysis.png)

- **GPU 使用率の改善:** GPU ビューまたは Windows パフォーマンス アナライザー (WPA) ツールを使って Visual Studio の GPU 使用率プロファイラーで取得されたトレースを開き、詳細な分析を行うことができます。 Windows パフォーマンス ツールキットがインストールされている場合、セッション概要の右下に WPA と GPU ビューの 2 つのハイパーリンクが表示されます。

  ![GPU 使用率](media/gpu-usage.png)

  このリンクを使用して GPU ビューで開いたトレースでは、同期された VS と GPU ビューのタイムラインのズームとパンがサポートされます。 VS のチェックボックスを使用すると、同期を有効にするかどうかを制御できます。

  ![GPU ビュー](media/gpu-view.png)
