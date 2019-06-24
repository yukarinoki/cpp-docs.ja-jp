---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e0d3af50015b77af297cbee22f439cd17d803de9
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344161"
---
# <a name="qspectre"></a>/Qspectre

特定のスペクター バリアント 1 のセキュリティ脆弱性を軽減するコンパイラの命令生成を指定します。

## <a name="syntax"></a>構文

> **/Qspectre**

## <a name="remarks"></a>Remarks

**/Qspectre** オプションは、Visual Studio 2017 バージョン 15.5.5 以降、および Visual Studio 2015 Update 3 から [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre) で使用できます。 指定すると、コンパイラによって特定の[スペクター セキュリティ脆弱性](https://spectreattack.com/spectre.pdf)を軽減する命令が挿入されます。 これらの脆弱性が呼び出される*予測実行のサイド チャネル攻撃*します。 多くのオペレーティング システムと Intel、AMD、および ARM プロセッサを含む、最新のプロセッサに影響します。

**/Qspectre** オプションは既定ではオフです。

最初のリリースでは、 **/Qspectre** オプションは最適化されたコードに対してのみ機能しました。 Visual Studio 2017 バージョン 15.7 以降では、 **/Qspectre** オプションはすべての最適化レベルでサポートされています。

スペクターの軽減策を含むバージョンの Microsoft Visual C++ ライブラリもリリースされています。 Visual Studio 2017 以降用のスペクター軽減済みライブラリは、Visual Studio インストーラーでダウンロードできます。 モ゙ ェャェォェ、**個々 のコンポーネント**タブ**コンパイラ、ビルド ツール、およびランタイム**、"Spectre 用ライブラリ"を名前であるとします。 軽減策が有効な DLL および静的ランタイム ライブラリのいずれも、次の Visual C++ ランタイムのサブセットに使用できます。VC++ のスタートアップ コード、vcruntime140、msvcp140、concrt140、および vcamp140。 Dll は、アプリケーションのローカル配置でのみサポートされます。 ビジュアルのコンテンツC++2017 以降ランタイム ライブラリ再頒布可能パッケージしていない変更されています。

MFC と ATL の Spectre 軽減ライブラリをインストールすることもできます。 モ゙ ェャェォェ、**個々 のコンポーネント**タブ**Sdk、ライブラリ、およびフレームワーク**します。

### <a name="applicability"></a>適用性

かどうかの信頼境界を越えるデータ、コードを操作し、使用することをお勧めします。、 **/Qspectre**オプションをリビルドし、できるだけ早くこの問題を軽減するために、コードを再デプロイします。 このようなコードの例では、コードの実行に影響を与える信頼されていない入力です。 などのリモート プロシージャは、コードを呼び出す信頼できない入力ファイルやファイルを解析または他のローカル プロセス間通信 (IPC) インターフェイスを使用します。 標準的なサンドボックスの手法では不十分な場合があります。 コードは、信頼境界を越えないを決定する前に、サンド ボックスを慎重に調査します。

### <a name="availability"></a>可用性

**/Qspectre**オプションは、すべての更新を Microsoft と Visual Studio 2017 バージョン 15.5.5 で使用できるC++、2018 年 1 月 23 日以降に行われたコンパイラ (MSVC)。 Visual Studio インストーラーを使用してコンパイラを更新し、スペクター軽減済みライブラリを個別のコンポーネントとしてインストールします。 **/Qspectre** オプションは、修正プログラムを介して Visual Studio 2015 Update 3 でも利用できます。 詳細については、[KB 4338871](https://support.microsoft.com/help/4338871) を参照してください。

Visual Studio 2017 バージョン 15.5 とすべてのプレビューの Visual Studio 2017 バージョン 15.6 のすべてのバージョン。 ドキュメントに未記載のオプションを含める **/d2guardspecload**します。 これは初期の動作に相当 **/Qspectre**します。 これらのバージョンのコンパイラでは、 **/d2guardspecload** を使用してコードに同じ軽減策を適用できます。 使用するようにビルドを更新することをお勧めします。 **/Qspectre**コンパイラ オプションをサポートします。 **/Qspectre**オプションは新しい軽減策を以降のバージョンのコンパイラでサポートも可能性があります。

### <a name="effect"></a>効果

**/Qspectre** オプションを指定すると、スペクター バリアント 1 の Bounds Check Bypass ([CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)) を軽減するコードが出力されます。 これは、投機的コード実行バリアとして動作する命令を挿入することで機能します。 プロセッサの投機の軽減に使用される具体的な命令は、プロセッサとそのマイクロアーキテクチャによって異なり、今後のバージョンのコンパイラでは変更される可能性があります。

有効にすると、 **/Qspectre**オプション、コンパイラは、予測実行が範囲チェックをバイパスがインスタンスを識別するためにしようとします。 これは、バリアの命令が挿入されます。 バリアント 1 のインスタンスを識別するために、コンパイラが行える分析に制限の注意すべき重要です。 そのため、バリアント 1 のすべての可能なインスタンスが インストルメント化される保証はありません **/Qspectre**します。

### <a name="performance-impact"></a>パフォーマンスへの影響

パフォーマンスに与える影響 **/Qspectre**いくつかのかなり大きなコード ベースでごくわずかであります。 ただし、保証はありません コードのパフォーマンスに影響を **/Qspectre**でも影響を受けません。 このオプションがパフォーマンスに与える影響を判断するには、コードのベンチマークを実行することをお勧めします。 軽減策はありません、パフォーマンスが重要なブロックまたはループに必要である場合は、選択的に無効にできます、軽減策を使用して、 [__declspec(spectre(nomitigation))](../../cpp/spectre.md)ディレクティブ。 のみをサポートするためのコンパイラでこのディレクティブを使用できない、 **/d2guardspecload**オプション。

### <a name="required-libraries"></a>必要なライブラリ

**/Qspectre**コンパイラ オプションは、Spectre の軽減策を提供するために構築、ランタイム ライブラリのバージョンを暗黙的にリンクするためのコードを生成します。 これらのライブラリは省略可能なコンポーネントであり、Visual Studio インストーラーを使用してインストールする必要があります。

- MSVC version *version_numbers* Libs for Spectre \[(x86 and x64) | (ARM) | (ARM64)]
- Visual C++ ATL for \[(x86/x64) | ARM | ARM64] with Spectre Mitigations
- Visual C++ MFC for \[x86/x64 | ARM | ARM64] with Spectre Mitigations

使用して、コードをビルドする場合 **/Qspectre**これらのライブラリは、ビルド システム レポートをインストールします。**警告 msb 8038。Spectre mitigation is enabled but Spectre mitigated libraries are not found"(警告 MSB8038: スペクターの軽減策は有効ですが、スペクター軽減済みライブラリが見つかりません)** が報告されます。 MFC または ATL コードをビルドするが失敗して、リンカーなどのエラーのレポート場合**致命的なエラー LNK1104: ファイル 'oldnames.lib' を開くことができません**、これらの不足しているライブラリが原因になる可能性があります。

### <a name="additional-information"></a>追加情報

詳細については、公式を参照してください。[予測実行のサイド チャネルの脆弱性を軽減するには、Microsoft セキュリティ アドバイザリ ADV180002、ガイダンス](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)します。 Intel の「[Speculative Execution Side Channel Mitigations](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)」(投機的実行サイド チャネルの軽減策) と ARM の「[Cache Speculation Side-channels](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)」(キャッシュ投機的サイドチャネル) のガイダンスも利用できます。 Spectre や Meltdown の軽減策の特定の Windows の概要については、次を参照してください。[の Windows システムで Spectre や Meltdown の軽減策のパフォーマンスに与える影響を理解する](https://www.microsoft.com/security/blog/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)します。 MSVC の軽減策が指す Spectre 脆弱性の概要については、次を参照してください。 [MSVC の、Spectre の軽減策](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc./)上、C++チームのブログ。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **[追加のオプション]** ボックスに **/Qspectre** コンパイラ オプションを入力します。 **[OK]** を選択して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
