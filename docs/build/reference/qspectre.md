---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e44416a44a9f772c17bc734d26c62ff87be775c8
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837414"
---
# <a name="qspectre"></a>/Qspectre

特定のスペクター バリアント 1 のセキュリティ脆弱性を軽減するコンパイラの命令生成を指定します。

## <a name="syntax"></a>構文

> **/Qspectre**

## <a name="remarks"></a>解説

**/Qspectre** オプションは、Visual Studio 2017 バージョン 15.5.5 以降、および Visual Studio 2015 Update 3 から [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre) で使用できます。 指定すると、コンパイラによって特定の[スペクター セキュリティ脆弱性](https://spectreattack.com/spectre.pdf)を軽減する命令が挿入されます。 *投機的実行サイドチャネル攻撃*と呼ばれるこれらの脆弱性は、多くのオペレーティング システムと、Intel 製、AMD 製、ARM 製のプロセッサを含む最新のプロセッサに影響を与えます。

**/Qspectre** オプションは既定ではオフです。

最初のリリースでは、 **/Qspectre** オプションは最適化されたコードに対してのみ機能しました。 Visual Studio 2017 バージョン 15.7 以降では、 **/Qspectre** オプションはすべての最適化レベルでサポートされています。

スペクターの軽減策を含むバージョンの Microsoft Visual C++ ライブラリもリリースされています。 Visual Studio 2017 以降用のスペクター軽減済みライブラリは、Visual Studio インストーラーでダウンロードできます。 これらは **[コンパイラ、ビルド ツール、およびランタイム]** の **[個別のコンポーネント]** タブにあり、名前には "Libs for Spectre" が含まれています。 軽減策が有効な DLL および静的ランタイム ライブラリのいずれも、次の Visual C++ ランタイムのサブセットに使用できます。VC++ のスタートアップ コード、vcruntime140、msvcp140、concrt140、および vcamp140。 DLL はアプリケーションのローカル展開にのみサポートされています。Visual C++ 2017 以降のランタイム ライブラリ再頒布可能ファイルの内容は変更されていません。 また、 **[SDK、ライブラリ、およびフレームワーク]** の **[個別のコンポーネント]** タブにある MFC と ATL 用のスペクター軽減済みライブラリをインストールすることもできます。

### <a name="applicability"></a>適用性

信頼境界を越えてデータを操作するコードの場合は、 **/Qspectre** オプションを使用してコードをリビルドして再展開し、できるだけ早くこの問題を軽減することをお勧めします。 信頼境界を越えてデータを操作するコードの例としては、実行に影響する可能性のある信頼されていない入力を読み込むコードがあります。たとえば、リモート プロシージャ呼び出しを行うコード、信頼されていない入力またはファイルを解析するコード、その他のローカルのプロセス間通信 (IPC) インターフェイスを使用するコードです。 標準的なサンドボックスの手法では不十分な場合があります。 コードが信頼境界を越えていないと判断する前に、サンドボックスを慎重に調べることをお勧めします。

### <a name="availability"></a>可用性

**/Qspectre** オプションは、Visual Studio 2017 バージョン 15.5.5 と、2018 年 1 月 23 日以降に作成された Microsoft MSVC コンパイラ (MSVC) のすべての更新プログラムで利用できます。 Visual Studio インストーラーを使用してコンパイラを更新し、スペクター軽減済みライブラリを個別のコンポーネントとしてインストールします。 **/Qspectre** オプションは、修正プログラムを介して Visual Studio 2015 Update 3 でも利用できます。 詳細については、[KB 4338871](https://support.microsoft.com/help/4338871) を参照してください。

Visual Studio 2017 バージョン 15.5 のすべてのバージョンと Visual Studio 2017 バージョン 15.6 のすべてのプレビューには、 **/d2guardspecload** というドキュメントに記載されていないオプションが含まれています。これは **/Qspectre** の初期動作と同じです。 これらのバージョンのコンパイラでは、 **/d2guardspecload** を使用してコードに同じ軽減策を適用できます。 **/Qspectre** オプションをサポートするコンパイラでは、使用するようにビルドを更新してください。 **/Qspectre** オプションは、コンパイラの今後のバージョンで新しい軽減策もサポートする可能性があります。

### <a name="effect"></a>効果

**/Qspectre** オプションを指定すると、スペクター バリアント 1 の Bounds Check Bypass ([CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)) を軽減するコードが出力されます。 これは、投機的コード実行バリアとして動作する命令を挿入することで機能します。 プロセッサの投機の軽減に使用される具体的な命令は、プロセッサとそのマイクロアーキテクチャによって異なり、今後のバージョンのコンパイラでは変更される可能性があります。

**/Qspectre** オプションが有効な場合、コンパイラでは、投機的実行によって境界チェックがバイパスされ、バリア命令が挿入される可能性があるインスタンスの特定が試行されます。 コンパイラでバリアント 1 のインスタンスを特定するために実行できる分析には制限があることに注意してください。 この理由から、 **/Qspectre** を指定しても、バリアント 1 の可能性があるすべてのインスタンスがインストルメント化される保証はありません。

### <a name="performance-impact"></a>パフォーマンスへの影響

**/Qspectre** のパフォーマンスへの影響は、いくつかの非常に大規模なコード ベースで無視できる程度であることが確認されていますが、 **/Qspectre** が指定されたコードのパフォーマンスへの影響がないという保証はありません。 このオプションがパフォーマンスに与える影響を判断するには、コードのベンチマークを実行することをお勧めします。 パフォーマンスが重要なブロックまたはループで、この軽減策が不要なことがわかっている場合は、[__declspec(spectre(nomitigation))](../../cpp/spectre.md) ディレクティブを使用してこの軽減策のみを無効にすることができます。 このディレクティブは、 **/d2guardspecload** オプションのみをサポートするコンパイラでは使用できません。

### <a name="required-libraries"></a>必要なライブラリ

**/Qspectre** コンパイラ オプションを指定すると、スペクターの軽減策を提供するために構築されたランタイム ライブラリのバージョンを暗黙的にリンクするコードが生成されます。 これらのライブラリは省略可能なコンポーネントであり、Visual Studio インストーラーを使用してインストールする必要があります。

- MSVC version *version_numbers* Libs for Spectre \[(x86 and x64) | (ARM) | (ARM64)]
- Visual C++ ATL for \[(x86/x64) | ARM | ARM64] with Spectre Mitigations
- Visual C++ MFC for \[x86/x64 | ARM | ARM64] with Spectre Mitigations

**/Qspectre** を使用してコードをビルドしてもこれらのライブラリがインストールされない場合は、ビルド システムから **"warning MSB8038: Spectre mitigation is enabled but Spectre mitigated libraries are not found"(警告 MSB8038: スペクターの軽減策は有効ですが、スペクター軽減済みライブラリが見つかりません)** が報告されます。 MFC コードまたは ATL コードのビルドに失敗し、リンカーから **"fatal error LNK1104: cannot open file 'oldnames.lib'"(致命的エラー LNK1104: ファイル 'oldnames.lib' を開けません)** などのエラーが報告される場合は、これらのライブラリが見つからないことが原因の可能性があります。

### <a name="additional-information"></a>追加情報

詳細については、公式の「[マイクロソフト セキュリティ アドバイザリ ADV180002 | 投機的実行のサイドチャネルの脆弱性を緩和するガイダンス](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)」を参照してください。 Intel の「[Speculative Execution Side Channel Mitigations](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)」(投機的実行サイド チャネルの軽減策) と ARM の「[Cache Speculation Side-channels](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)」(キャッシュ投機的サイドチャネル) のガイダンスも利用できます。 Windows 固有のスペクターとメルトダウンの軽減策の概要については、Microsoft Secure ブログの「[Understanding the performance impact of Spectre and Meltdown mitigations on Windows Systems](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)」(スペクターとメルトダウンの軽減策が Windows システムに対して与えるパフォーマンスへの影響の概要) を参照してください。 MSVC の軽減策で対応しているスペクターの脆弱性の概要については、Visual C++ チーム ブログの「[Spectre mitigations in MSVC](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./)」(MSVC でのスペクターの軽減策) を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **[追加のオプション]** ボックスに **/Qspectre** コンパイラ オプションを入力します。 **[OK]** を選択して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
