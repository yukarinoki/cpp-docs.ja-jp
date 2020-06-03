---
title: MIDL コンパイラのプロパティ ページ
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 57498a01-fccc-4a0e-a036-6ff702f83126
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.AdditionalMetadataDirectories
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.MultiProcMIDL
- VC.Project.VCMidlTool.OutputDirectory
- VC.Project.VCMidlTool.WinmdFileName
- VC.Project.VCMidlTool.HeaderFileName
- VC.Project.VCMidlTool.DLLDataFileName
- VC.Project.VCMidlTool.InterfaceIdentifierFileName
- VC.Project.VCMidlTool.ProxyFileName
- VC.Project.VCMidlTool.GenerateTypeLibrary
- VC.Project.VCMidlTool.TypeLibraryName
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.TypeLibFormat
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.PreendWithABINamepsace
- VC.Project.VCMidlTool.ValidateParameters
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.MinimumTargetSystem
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d6833230baca892836c187799df7f0658aa16772
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336250"
---
# <a name="midl-property-pages"></a>[MIDL] プロパティ ページ

MIDL プロパティ ページは、 のアイテム プロパティとして使用できます。COM を使用する C++ プロジェクトの IDL ファイル。 [MIDL コンパイラ](/windows/win32/midl/using-the-midl-compiler-2)を構成するために使用します。 C++ プロジェクト用の MIDL オプションにプログラムでアクセスする方法の詳細については、<xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> オブジェクトに関するページを参照してください。 [「MIDL コマンド ラインの一般的な構文](/windows/win32/midl/general-midl-command-line-syntax)」も参照してください。

## <a name="general-property-page"></a>[全般] プロパティ ページ

### <a name="preprocessor-definitions"></a>プリプロセッサの定義

MIDL マクロ ([/D](/windows/win32/midl/-d)) マクロ\[\]を含む 1 つまたは複数の定義を指定します。

### <a name="additional-include-directories"></a>追加のインクルード ディレクトリ

インクルード パス ([/I](/windows/win32/midl/-i)\[パス\]) に追加する 1 つ以上のディレクトリを指定します。

### <a name="additional-metadata-directories"></a>追加のメタデータ ディレクトリ

ファイル ([/metadata_dir](/windows/win32/midl/-metadata-dir)\[パス\]) を含むディレクトリを指定します。

### <a name="enable-windows-runtime"></a>Windows ランタイムを有効にする

Windows ランタイム セマンティクスを有効にして、Windows メタデータ ファイル ([/winrt](/windows/win32/midl/-winrt)) を作成します。

### <a name="ignore-standard-include-path"></a>標準インクルードパスを無視

現在のディレクトリと INCLUDE ディレクトリ ([/no_def_idir](/windows/win32/midl/-no-def-idir)) は無視します。

### <a name="mktyplib-compatible"></a>互換性のある MkTypLib

mktyplib.exe バージョン 2.03 ([/mktyplib203](/windows/win32/midl/-mktyplib203)) との互換性を強制します。

### <a name="warning-level"></a>警告レベル

MIDL コード エラーの厳密さを選択します ([/W](/windows/win32/midl/-w))。

**選択肢**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>[警告をエラーとして扱う]

MIDL がすべての警告をエラー ([/WX](/windows/win32/midl/-wx)) として扱うようにします。

### <a name="suppress-startup-banner"></a>著作権情報の非表示

スタートアップ バナーと情報メッセージ ([/nologo](/windows/win32/midl/-nologo)) の表示を抑制します。

### <a name="c-compiler-char-type"></a>C コンパイラの文字タイプ

生成されたコードのコンパイルに使用される C コンパイラの既定の文字型を指定します。 ([/char](/windows/win32/midl/-char)符号付き|符号なし|ascii7)。

**選択肢**

- **署名済**み - 署名済み
- **符号なし**- 未署名
- **アスキー** - アスキー

### <a name="target-environment"></a>ターゲット環境

対象とする環境を指定します[(/env](/windows/win32/midl/-env) arm32|win32|ia64|x64)。

**選択肢**

- **設定されていません**- Win32
- **マイクロソフトウィンドウズ 32ビット**- Win32
- **マイクロソフトのウィンドウズ 64 ビット オン イタニウム**- IA64
- **マイクロソフト ウィンドウズ アーム**- アーム
- **マイクロソフト ウィンドウズ ARM64** - ARM64
- **マイクロソフトのウィンドウズ 64 ビット x64 - X64**

### <a name="generate-stubless-proxies"></a>スタブレス プロキシの生成

オブジェクト インターフェイス ([/Oicf](/windows/win32/midl/-oi)、 [/Oif](/windows/win32/midl/-oi) ) の拡張とスタブレス プロキシを備えた完全に解釈されたスタブを生成します。

### <a name="suppress-compiler-warnings"></a>コンパイラ警告の非表示

コンパイラの警告メッセージを表示しない ([/no_warn](/windows/win32/midl/-no-warn))。

### <a name="application-configuration-mode"></a>アプリケーション構成モード

IDL ファイル内の選択した ACF 属性を許可する ([/app_config](/windows/win32/midl/-app-config))。

### <a name="locale-id"></a>ロケール ID

入力ファイル、ファイル名、およびディレクトリ パス[(/lcid](/windows/win32/midl/-lcid) DECIMAL) の LCID を指定します。

### <a name="multi-processor-compilation"></a>マルチプロセッサ コンパイル

複数のインスタンスを同時に実行します。

## <a name="output-property-page"></a>出力プロパティ ページ

### <a name="output-directory"></a>出力ディレクトリ

出力ディレクトリ[(/out](/windows/win32/midl/-out) [ディレクトリ]) を指定します。

### <a name="metadata-file"></a>メタデータ ファイル

生成されるメタデータ ファイルの名前[(/winmd](/windows/win32/midl/-winmd)ファイル名) を指定します。

### <a name="header-file"></a>ヘッダー ファイル

生成されるヘッダー ファイルの名前[(/h](/windows/win32/midl/-h)ファイル名) を指定します。

### <a name="dlldata-file"></a>Dll データ ファイル

DLLDATA ファイルの名前[(/dlldata](/windows/win32/midl/-dlldata)ファイル名) を指定します。

### <a name="iid-file"></a>IID ファイル

インターフェイス識別子ファイル[(/iid](/windows/win32/midl/-iid)ファイル名) の名前を指定します。

### <a name="proxy-file"></a>プロキシ ファイル

プロキシ ファイルの名前[(/proxy](/windows/win32/midl/-proxy)ファイル名) を指定します。

### <a name="generate-type-library"></a>タイプ ライブラリの生成

タイプ ライブラリを生成しないように指定します ([/notlb] を no にします)。

### <a name="type-library"></a>タイプ ライブラリ

タイプ ライブラリ ファイルの名前[(/tlb](/windows/win32/midl/-tlb)ファイル名) を指定します。

### <a name="generate-client-stub-files"></a>クライアント スタブ ファイルの生成

クライアント スタブ ファイルのみを生成します[(/クライアント](/windows/win32/midl/-client)[スタブ|なし])。

**選択肢**

- **スタブ**- スタブ
- **なし**- なし

### <a name="generate-server-stub-files"></a>サーバー スタブ ファイルの生成

サーバー スタブ ファイルのみを生成します ([/server](/windows/win32/midl/-server) [スタブ|なし])。

**選択肢**

- **スタブ**- スタブ
- **なし**- なし

### <a name="client-stub-file"></a>クライアント スタブ ファイル

クライアント スタブ ファイル[(/cstub](/windows/win32/midl/-cstub) [ファイル]) を指定します。

### <a name="server-stub-file"></a>サーバー スタブ ファイル

サーバー スタブ ファイル[(/sstub](/windows/win32/midl/-sstub) [ファイル]) を指定します。

### <a name="type-library-format"></a>タイプ ライブラリ形式

タイプ ライブラリ ファイル形式 ([/oldtlb|/newtlb]) を指定します。

**選択肢**

- **新しい書式**- 新しい書式
- **古い形式**- 古い形式

## <a name="advanced-property-page"></a>[詳細プロパティ] ページ

### <a name="c-preprocess-options"></a>C 前処理オプション

C コンパイラ プリプロセッサ[(/cpp_opt](/windows/win32/midl/-cpp-opt)スイッチ) に渡すスイッチを指定します。

### <a name="undefine-preprocessor-definitions"></a>指定したプリプロセッサ定義の無効化

MIDL マクロ ([/U](/windows/win32/midl/-U) [マクロ]) を含む、1 つ以上の未定義を指定します。

### <a name="enable-error-checking"></a>エラー チェックを有効にする

エラー チェック オプションを選択します ([エラー all|none])。

**選択肢**

- **カスタムを有効に**する - すべて
- **すべて**- すべて
- **なし**- なし

### <a name="check-allocations"></a>配賦の確認

メモリ不足エラー[(/エラー](/windows/win32/midl/-error)割り当て) を確認します。

### <a name="check-bounds"></a>境界の確認

サイズと伝送長の指定を確認する ([/エラー](/windows/win32/midl/-error) bounds_check)。

### <a name="check-enum-range"></a>列挙範囲の確認

列挙値が許容範囲内に入ることを確認します ([/エラー](/windows/win32/midl/-error)列挙 )。

### <a name="check-reference-pointers"></a>参照ポインタの確認

ref ポインターが null 以外の場合[(/エラー](/windows/win32/midl/-error) ref) を確認します。

### <a name="check-stub-data"></a>スタブ データの確認

サーバー側スタブ データの有効性[(/エラー](/windows/win32/midl/-error) stub_data) の追加チェックを行います。

### <a name="prepend-with-abi-namespace"></a>'ABI' 名前空間を先頭に付け

'ABI' 名前空間をすべての型の前に付ける。  ([/ns_prefix](/windows/win32/midl/-ns-prefix))。

### <a name="validate-parameters"></a>パラメーターの検証

パラメータを検証するための追加情報を生成します ([/強い](/windows/win32/midl/-robust) | [/no_robust](/windows/win32/midl/-no-robust))。

### <a name="struct-member-alignment"></a>構造体メンバーの配置

ターゲット システム (/ZpN) の構造体のパッキング レベルを指定します。

**選択肢**

- **設定されていません**- 設定されていません
- **1 バイト**- Zp1
- **2 バイト**- Zp2
- **4 バイト**- Zp4
- **8 バイト**- Zp8

### <a name="redirect-output"></a>リダイレクト出力

画面からファイル[(/o](/windows/win32/midl/-o)ファイル) に出力をリダイレクトします。

### <a name="minimum-target-system"></a>最小ターゲットシステム

最小ターゲット システム[(/ターゲット](/windows/win32/midl/-target)文字列) を設定します。
