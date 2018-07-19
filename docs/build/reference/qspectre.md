---
title: /Qspectre |Microsoft ドキュメント
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
ms.openlocfilehash: 3d87850ae5413ccf876eb4d4b44b34e34527ef9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379420"
---
# <a name="qspectre"></a>/Qspectre

Spectre バリアント 1 セキュリティの脆弱性を軽減するために手順のコンパイラ生成を指定します。

## <a name="syntax"></a>構文

> **/Qspectre**

## <a name="remarks"></a>コメント

**/Qspectre**オプションは、特定の操作を軽減するために命令を挿入コンパイラ[Spectre セキュリティの脆弱性](https://spectreattack.com/spectre.pdf)です。 これらの脆弱性と呼ばれる*予測実行サイド チャネル攻撃*多くのオペレーティング システムと Intel、AMD からのプロセッサを含む、最新のプロセッサに影響を与える、および ARM です。

**/Qspectre**オプションは既定でオフになっています。

最初のリリースで、 **/Qspectre**オプションは、最適化されたコードでのみ機能します。 最適化オプションのいずれかと、コードをコンパイルすることを確認する必要があります (たとえば、 [/O1、/O2 または](o1-o2-minimize-size-maximize-speed.md)は対象外[/Od](od-disable-debug.md)) 緩和策が適用されるかどうかを確認します。 同様に、使用するすべてのコードを検査[#pragma optimize ("stg"、オフ)](../../preprocessor/optimize.md)です。

### <a name="applicability"></a>適用性

かどうか、コードの信頼境界を越えるデータを操作し、使用することをお勧め、 **/Qspectre**リビルドして直ちにこの問題を軽減するために、コードを再配置するにはオプションです。 信頼境界を越えるデータを操作するコードの例は、実行に影響を与える信頼されていない入力を読み込むコード、コードを使用してリモート プロシージャを呼び出し、信頼されていない入力ファイルやファイルを解析など、他のローカル プロセスの間を使用して通信 (IPC) インターフェイス。 サンド ボックス化の標準的な手法は十分でない可能性があります。 サンド ボックスは、コードが信頼境界を越えないを決定する前に慎重に調査する必要があります。

### <a name="availability"></a>可用性

**/Qspectre**オプションは、Visual Studio 2017 バージョン 15.5.5 および 2018 年 1 月 23日以降に行われたすべての更新を Microsoft Visual C コンパイラ (MSVC) で使用できます。

15.5 とすべてのプレビューの Visual Studio version 15.6 が含まれているドキュメントに未記載のオプションには Visual Studio 2017 バージョンのすべてのバージョン **/d2guardspecload**、つまりと等価の初期動作 **/Qspectre**. 使用することができます **/d2guardspecload**これらのバージョンのコンパイラで自分のコードに同じの緩和策を適用します。 使用するようにビルドを更新してください。 **/Qspectre** ; オプションをサポートするコンパイラで、 **/Qspectre**オプションは、以降のバージョンのコンパイラで新しい緩和策をサポートも可能性があります。

### <a name="effect"></a>効果

**/Qspectre**オプションは、境界チェックのバイパス、バリアント型 1、労力を軽減するためにコードを出力[CVE 2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753)です。 この機能は、予測のコード実行のバリアとして機能する命令の挿入で機能します。 プロセッサ推理を軽減するために使用される具体的な指示はプロセッサとのマイクロ アーキテクチャに依存し、将来のバージョンのコンパイラで変更可能性があります。

ときに、 **/Qspectre**オプションが有効になっている、コンパイラは予測の実行の範囲チェックをバイパスする可能性があり、バリアの命令を挿入します。 ここでのインスタンスを識別しようとしています。 バリアント 1 のインスタンスを識別する、コンパイラに実行する分析に制限があることに注意してくださいに重要です。 そのため、バリアント 1 のすべての可能なインスタンスが インストルメント化されているという保証はありません **/Qspectre**です。

### <a name="performance-impact"></a>パフォーマンスに与える影響

パフォーマンスに与える影響 **/Qspectre**わずかいくつかの非常に大きなコード ベースである場合に、発生の保証はありませんその下にあるコードのパフォーマンスが **/Qspectre**でも影響を受けません。 パフォーマンス オプションの影響を決定するコードをベンチマーク必要があります。 パフォーマンスが重要なブロックまたはループではの緩和策が必要ないことがわかっている場合、軽減選択的に無効にできますを使用して、 [__declspec(spectre(nomitigation))](../../cpp/spectre.md)ディレクティブです。 このディレクティブはのみをサポートするコンパイラでは使用できません、 **/d2guardspecload**オプション。

### <a name="additional-information"></a>追加情報

詳細については、公式をご覧ください。[予測実行サイド チャネル上の脆弱性を軽減するには、マイクロソフト セキュリティ アドバイザリ ADV180002、ガイダンス](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002)です。 Intel から使用可能なガイダンスも[予測実行側チャネルの緩和策](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf)、および ARM、[キャッシュ推理側チャネル](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf)です。 Spectre とメルトダウンの緩和策の特定の Windows 概要については、次を参照してください。 [Windows システムで Spectre とメルトダウンの緩和策のパフォーマンスに与える影響を理解する](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/)Microsoft セキュリティで保護されたブログ。 MSVC 緩和策によってアドレス指定される Spectre 脆弱性の概要については、次を参照してください。 [MSVC で Spectre 緩和策](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./)Visual c チーム ブログでします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 入力、 **/Qspectre**コンパイラ オプション、**追加オプション**ボックス。 選択**OK**変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)  
[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
