---
title: リンカー オプション
ms.date: 08/20/2018
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 63cfa784242af1f737c116629a29be5ad77af31d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415202"
---
# <a name="linker-options"></a>リンカー オプション

LINK.exe は、COFF (Common Object File Format) オブジェクト ファイルとライブラリをリンクし、実行可能ファイル (.exe) やダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。

LINK.exe のオプションの一覧を次の表に示します。 LINK の詳細については、下記を参照してください。

- [コンパイラで制御される LINK オプション](../../build/reference/compiler-controlled-link-options.md)

- [LINK の入力ファイル](../../build/reference/link-input-files.md)

- [LINK 出力](../../build/reference/link-output.md)

- [予約語](../../build/reference/reserved-words.md)

コマンドラインでリンカー オプションは; 大文字小文字を区別できません。たとえば、/base と/BASE は同じ意味です。 コマンド ラインまたは Visual Studio で各オプションを指定する方法の詳細については、そのオプションのドキュメントを参照してください。

[comment](../../preprocessor/comment-c-cpp.md) プラグマを使用して、一部のリンカー オプションを指定できます。

|オプション|目的|
|------------|-------------|
|[@](../../build/reference/at-specify-a-linker-response-file.md)|応答ファイルを指定します。|
|[/ALIGN](../../build/reference/align-section-alignment.md)|各セクションのアラインメントを指定します。|
|[/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|DLL をバインディングできないことを指定します。|
|[/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|マニフェスト検索の動作を指定します。|
|[/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|アプリケーションが appcontainer プロセス環境内で実行される必要があるかどうかを指定します。|
|[/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)|<xref:System.Diagnostics.DebuggableAttribute> をマネージド イメージに追加します。|
|[/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|マネージド リソースへのリンクを作成します。|
|[/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|MSIL (Microsoft Intermediate Language) モジュールをアセンブリにインポートする必要があることを指定します。|
|[/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|マネージド リソース ファイルをアセンブリに埋め込みます。|
|[/BASE](../../build/reference/base-base-address.md)|プログラムのベース アドレスを設定します。|
|[/CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|リンク時のコード生成を指定するときに、最適化およびコード生成に使用する cl.exe スレッド数を設定します。|
|[/CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)|CLR イメージの種類 (IJW、純粋、または安全) を設定します。|
|[/CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke 機構を通じて呼び出された関数の最終エラー コードを保持します。|
|[/CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|CLR プログラムのエントリ ポイントに適用するスレッド処理属性を指定します。|
|[/CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|マネージド コードからネイティブ DLL への呼び出しを行う、リンカーによって生成された PInvoke スタブに、SuppressUnmanagedCodeSecurity 属性を適用するかどうかを指定します。|
|[/DEBUG](../../build/reference/debug-generate-debug-info.md)|デバッグ情報を作成します。|
|[/DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|デバッグ情報に含めるデータを指定します。|
|[/DEF](../../build/reference/def-specify-module-definition-file.md)|モジュール定義 (.def) ファイルをリンカーに渡します。|
|[/DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|外部参照を解決するときに、指定したライブラリを検索します。|
|[/DELAY](../../build/reference/delay-delay-load-import-settings.md)|DLL の遅延読み込みを制御します。|
|[/DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|指定した DLL に遅延読み込みを発生させます。|
|[/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|アセンブリに部分署名します。|
|[/DEPENDENTLOADFLAG](dependentloadflag.md)|依存 DLL の読み込みには、既定のフラグを設定します。|
|[/DLL](../../build/reference/dll-build-a-dll.md)|DLL をビルドします。|
|[/DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|カーネル モード ドライバーを作成します。|
|[/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|ASLR (Address Space Layout Randomization) 機能を使用してロード時にランダムに再ベースできる実行可能イメージを生成するかどうかを指定します。|
|[/ENTRY](../../build/reference/entry-entry-point-symbol.md)|開始アドレスを設定します。|
|[/errorReport](../../build/reference/errorreport-report-internal-linker-errors.md)|内部リンカー エラーを Microsoft に報告します。|
|[/EXPORT](../../build/reference/export-exports-a-function.md)|関数をエクスポートします。|
|[/FILEALIGN](../../build/reference/filealign.md)|指定された値の倍数で出力ファイル内のセクションを配置します。|
|[/FIXED](../../build/reference/fixed-fixed-base-address.md)|指定のベース アドレスだけに読み込まれるプログラムを作成します。|
|[/FORCE](../../build/reference/force-force-file-output.md)|未解決のシンボルまたは複数定義のシンボルがある場合でも、リンクを強制的に終了します。|
|[/FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|ホット パッチ可能なイメージを作成します。|
|[/GENPROFILE、/FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|これらのオプションは、ガイド付き最適化のプロファイル (PGO) をサポートするために、どちらもリンカーによる .pgd ファイルの生成を指定します。 /GENPROFILE と /FASTGENPROFILE は、それぞれに異なる既定のパラメーターを使用します。|
|[/GUARD](../../build/reference/guard-enable-guard-checks.md)|制御フロー ガードによる保護を有効にします。|
|[/HEAP](../../build/reference/heap-set-heap-size.md)|ヒープ サイズをバイト単位で設定します。|
|[/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md)|高エントロピの 64 ビット ASLR (Address Space Layout Randomization) のサポートを指定します。|
|[/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)|.idl ファイル名およびその他の MIDL の出力ファイル名を指定します。|
|[/IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|指定されたリンカー警告の出力を抑制します。|
|[/IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|.idl ファイル内に属性情報を挿入しません。|
|[/IMPLIB](../../build/reference/implib-name-import-library.md)|既定のインポート ライブラリ名をオーバーライドします。|
|[/INCLUDE](../../build/reference/include-force-symbol-references.md)|シンボルを明示的に参照します。|
|[/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|インクリメンタル リンクの処理方法を制御します。|
|[/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|モジュールが読み込み時に署名の確認を要求することを指定します。|
|[/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|アセンブリに署名するためのキー コンテナーを指定します。|
|[/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|アセンブリに署名するキーまたはキー ペアを指定します。|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|アプリケーションが 2 GB を超えるアドレスをサポートしていることをコンパイラに指定します。|
|[/LIBPATH](../../build/reference/libpath-additional-libpath.md)|環境ライブラリ パスの前に検索するパスを指定します。|
|[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|リンク時のコード生成を指定します。|
|[/MACHINE](../../build/reference/machine-specify-target-platform.md)|ターゲット プラットフォームを指定します。|
|[/MANIFEST](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|side-by-side マニフェスト ファイルを作成し、バイナリに埋め込むことができるようにします。|
|[/MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|指定します、 \<dependentAssembly > セクションで、マニフェスト ファイル。|
|[/MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|マニフェスト ファイルの既定の名前を変更します。|
|[/MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|リンカーが処理を行い、バイナリに埋め込むための、マニフェスト入力ファイルを指定します。 このオプションを複数回使用して、複数のマニフェストの入力ファイルを指定できます。|
|[/MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|ユーザー アカウント制御 (UAC) 情報をプログラム マニフェストに組み込むかどうかを指定します。|
|[/MAP](../../build/reference/map-generate-mapfile.md)|マップファイルを作成します。|
|[/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|指定した情報をマップ ファイルに格納します。|
|[/MERGE](../../build/reference/merge-combine-sections.md)|セクションを結合します。|
|[/MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|MIDL コマンド ライン オプションを指定します。|
|[/NATVIS](../../build/reference/natvis-add-natvis-to-pdb.md)|PDB に Natvis ファイルからデバッガー ビジュアライザーを追加します。|
|[/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|.NET Framework アセンブリを作成しません。|
|[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|外部参照を解決するときに、すべてのまたは指定した既定のライブラリを無視します。|
|[/NOENTRY](../../build/reference/noentry-no-entry-point.md)|リソースだけの DLL を作成します。|
|[/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|開始メッセージを表示しません。|
|[/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Windows データ実行防止機能との互換性が確認済みとして実行可能ファイルをマークします。|
|[/OPT](../../build/reference/opt-optimizations.md)|LINK の最適化を制御します。|
|[/ORDER](../../build/reference/order-put-functions-in-order.md)|指定された順序で COMDAT をイメージに取り込みます。|
|[/OUT](../../build/reference/out-output-file-name.md)|出力ファイル名を指定します。|
|[/PDB](../../build/reference/pdb-use-program-database.md)|プログラム データベース (PDB) ファイルを作成します。|
|[/PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|別の場所を使用して PDB ファイルを保存します。|
|[/PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|プログラム データベース (PDB) ファイルの作成時にプライベート シンボルを含めません。|
|[/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|ガイド付き最適化のプロファイル用の .pgd ファイルを指定します。|
|[/POGOSAFEMODE](../../build/reference/pogosafemode-linker-option.md)|**古い**スレッド セーフのインストルメント化 PGO ビルドを作成します。|
|[/PROFILE](../../build/reference/profile-performance-tools-profiler.md)|パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。|
|[/RELEASE](../../build/reference/release-set-the-checksum.md)|.exe ヘッダーにチェックサムを設定します。|
|[/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)|安全な例外ハンドラーのテーブルがイメージに含まれるように指定します。|
|[/SECTION](../../build/reference/section-specify-section-attributes.md)|セクションの属性をオーバーライドします。|
|[/SOURCELINK](../../build/reference/sourcelink.md)|Pdb ファイルに追加する SourceLink ファイルを指定します。|
|[/STACK](../../build/reference/stack-stack-allocations.md)|スタック サイズをバイト単位で設定します。|
|[/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|MS-DOS スタブ プログラムを Win32 プログラムにアタッチします。|
|[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|オペレーティング システムに対して、.exe ファイルの実行方法を指定します。|
|[/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|リンカー出力をスワップ ファイルにコピーしてから実行します。|
|[/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|リンカーによって生成されたタイプ ライブラリのリソース ID を指定します。|
|[/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|.tlb ファイル名およびその他の MIDL の出力ファイル名を指定します。|
|[/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|ターミナル サーバーでの実行専用のアプリケーションを作成します。|
|[/USEPROFILE](../../build/reference/useprofile.md)|最適化されたイメージを作成するには、最適化トレーニング データをプロファイル ガイド付きの使用。|
|[/VERBOSE](../../build/reference/verbose-print-progress-messages.md)|リンカーの進行状況メッセージを出力します。|
|[/VERSION](../../build/reference/version-version-information.md)|バージョン番号を割り当てます。|
|[/WHOLEARCHIVE](../../build/reference/wholearchive-include-all-library-object-files.md)|指定された静的ライブラリからすべてのオブジェクト ファイルが含まれています。|
|[/WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Windows ランタイム メタデータ ファイルの生成を有効にします。|
|[/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)|[/WINMD](../../build/reference/winmd-generate-windows-metadata.md) のリンカー オプションによって生成される Windows のランタイム メタデータ (winmd) の出力ファイルの名前を指定します。|
|[/WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Windows ランタイム メタデータに署名するキーまたはキー ペアを指定します。|
|[/WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Windows メタデータ ファイルに署名するキー コンテナーを指定します。|
|[/WINMDDELAYSIGN](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|winmd ファイルに公開キーを設定して、Windows のランタイム メタデータ (.winmd) ファイルに部分的に署名します。|
|[/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|リンカー警告をエラーとして扱います。|

詳細については、「 [Compiler-Controlled LINK Options](../../build/reference/compiler-controlled-link-options.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)
