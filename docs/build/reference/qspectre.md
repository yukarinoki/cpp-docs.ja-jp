---
title: /Qspectre |Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec3509b71d78221c3e15607d34f674fc38d9f635
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43130990"
---
# <a name="qspectre"></a>/Qspectre

Spectre バリアント 1 セキュリティの脆弱性を軽減するための手順のコンパイラ生成を指定します。

## <a name="syntax"></a>構文

> **/Qspectre**

## <a name="remarks"></a>Remarks

**/Qspectre**オプションは、Visual Studio 2017 バージョン 15.7 で使用できる以降。 特定の操作を軽減するために手順を挿入するコンパイラが、その[Spectre セキュリティの脆弱性](https://spectreattack.com/spectre.pdf)します。 これらの脆弱性と呼ばれる*予測実行のサイド チャネル攻撃*に影響する多くのオペレーティング システムと最新のプロセッサ、AMD、intel プロセッサを含む、および ARM です。

**/Qspectre**オプションは既定でオフです。

最初のリリースで、 **/Qspectre**オプションは、最適化されたコードでのみ機能します。 最適化のオプションを使用してコードをコンパイルすることを確認する必要があります (たとえば、 [/O1、/O2、または](o1-o2-minimize-size-maximize-speed.md)なく[/Od](od-disable-debug.md))、軽減策が適用されるかどうかを確認します。 同様に、使用するコードを検査[#pragma optimize ("stg"、オフ)](../../preprocessor/optimize.md)します。

### <a name="applicability"></a>適用性

信頼境界を越えるデータ、コードを操作し、使用することをお勧めします。 場合、 **/Qspectre**を再構築し、できるだけ早くこの問題を軽減するために、コードを再デプロイするにはオプションです。 などを使用してリモート プロシージャ コードを呼び出す信頼できない入力ファイルやファイルを解析または他の間でローカルのプロセスを使用して、信頼境界を越えるデータを操作するコードの例には実行に影響を与える信頼できない入力を読み込むコードが含まれます通信 (IPC) インターフェイス。 サンド ボックス化の標準的な手法は十分でない可能性があります。 コードが信頼境界を越えないことを決定する前に、サンド ボックスを注意深く調べる必要があります。

### <a name="availability"></a>可用性

**/Qspectre**オプションは Visual Studio 2017 バージョン 15.5.5、2018 年 1 月 23 日以降に行われたすべての更新を Microsoft Visual C コンパイラ (MSVC) で使用できます。

15.5 とすべてのプレビューの Visual Studio バージョン 15.6 に文書化されていないオプションでは、既に含まれている Visual Studio 2017 バージョンのすべてのバージョン **/d2guardspecload**、つまりと同等の初期動作 **/Qspectre**. 使用することができます **/d2guardspecload**これらのバージョンのコンパイラでは、コードに同じの軽減策を適用します。 使用するようにビルドを更新してください。 **/Qspectre** ; オプションをサポートするためのコンパイラで、 **/Qspectre**オプションは新しい軽減策を以降のバージョンのコンパイラでサポートも可能性があります。

### <a name="effect"></a>効果

**/Qspectre**オプション亡霊バリアント 1、境界チェックのバイパスを軽減するためにコードを出力する[CVE 2017-5753 に対する](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)します。 投機的なコード実行のバリアとして機能する命令の挿入することによって動作します。 プロセッサ投機を軽減するために使用される特定の手順では、プロセッサとそのマイクロ アーキテクチャに依存およびの将来のバージョンのコンパイラで変更される可能性です。

ときに、 **/Qspectre**オプションが有効になっている、コンパイラは予測実行が範囲チェックが無視され、バリアの命令を挿入のインスタンスを識別しようとしています。 コンパイラは、バリアント 1 のインスタンスを識別するために実行できる分析に制限があることに注意してください。 重要です。 そのため、バリアント 1 のすべての可能なインスタンスが インストルメント化される保証はありません **/Qspectre**します。

### <a name="performance-impact"></a>パフォーマンスに与える影響

パフォーマンスに与える影響 **/Qspectre**いくつかの非常に大きなコード ベースで無視できること確認されていますが、保証はありません コードのパフォーマンスに影響を **/Qspectre**でも影響を受けません。 パフォーマンス オプションの効果を決定するコードのベンチマークを実行する必要があります。 使用して、軽減策を選択的に無効にパフォーマンスが重要なブロックまたはループ、軽減策が必要ないことがわかっている場合、 [__declspec(spectre(nomitigation))](../../cpp/spectre.md)ディレクティブ。 このディレクティブはのみをサポートするためのコンパイラで使用できません、 **/d2guardspecload**オプション。

### <a name="required-libraries"></a>必要なライブラリ

**/Qspectre**コンパイラ オプションは、暗黙的に組み込まれている Spectre の軽減策を提供するランタイム ライブラリのバージョンをリンクするコードを生成します。 これらのライブラリは、省略可能なコンポーネント、Visual Studio インストーラーを使用してインストールする必要があります。

- Vc++ 2017 バージョン*version_number* (x86 および x64)、Spectre 用ライブラリ
- Spectre の軽減策を含む Visual C++ ATL (x86 または x64)
- Spectre の軽減策を含む x86 または x64 用 Visual C++ MFC

使用して、コードをビルドする場合 **/Qspectre**おり、これらのライブラリがないビルド システム レポートをインストールします。**警告 msb 8038: Spectre の軽減策が有効になっているが、Spectre 軽減ライブラリが見つかりません**します。 場合は、MFC または ATL コードのビルドに失敗して、リンカーなどのエラーのレポート**致命的なエラー LNK1104: ファイル 'oldnames.lib' を開くことができません**、これらの不足しているライブラリが原因になる可能性があります。

### <a name="additional-information"></a>追加情報

詳細については、公式ページをご覧ください[予測実行のサイド チャネルの脆弱性を軽減するには、Microsoft セキュリティ アドバイザリ ADV180002、ガイダンス](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)します。 ガイダンスは、Intel から入手できるも[投機実行サイド チャネルの軽減策](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)、および ARM、[キャッシュ推理のサイド チャネル](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)します。 Spectre や Meltdown の軽減策の特定の Windows の概要については、次を参照してください。[の Windows システムで Spectre や Meltdown の軽減策のパフォーマンスに与える影響を理解する](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)Microsoft セキュリティで保護されたブログ。 MSVC の軽減策が指す Spectre 脆弱性の概要については、次を参照してください。 [MSVC の、Spectre の軽減策](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./)Visual c チーム ブログにします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 入力、 **/Qspectre**コンパイラ オプションで、**追加オプション**ボックス。 選択**OK**して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)  
[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
