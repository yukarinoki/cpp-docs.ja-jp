---
title: /OPT (最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc9f7f66b9bd0ee2c0da65d17eac33e1cbc8c316
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2018
---
# <a name="opt-optimizations"></a>/OPT (最適化)

LINK がビルド時に実行する最適化を制御します。

## <a name="syntax"></a>構文

> **/OPT:**{**REF** | **NOREF**}<br/>
> **/OPT:**{**ICF**[**=**_イテレーション_] |**NOICF**}<br/>
> **/OPT:**{**LBR** | **NOLBR**}

## <a name="arguments"></a>引数

**REF** &AMP;#124; **NOREF**

**/Opt:ref による**排除関数とデータが参照されていません。**/OPT:NOREF**関数および参照されないデータを保持します。

未参照のパッケージ化された関数と呼ばれる、データ リンクの削除/opt:ref によるを有効にすると、 *Comdat*です。 この最適化は、中間 COMDAT 除去として知られています。 **/Opt:ref による**もオプションではインクリメンタル リンクを無効になります。

インライン関数とクラス宣言内で定義されたメンバー関数は、Comdat では常にします。 すべてのオブジェクト ファイルで関数が行われる Comdat を使用してコンパイルされる場合、 [/Gy](../../build/reference/gy-enable-function-level-linking.md)オプション。 配置する**const** 、Comdat でデータをする必要がありますを使用して宣言`__declspec(selectany)`です。 データの削除または圧縮を指定する方法については、次を参照してください。 [selectany](../../cpp/selectany.md)です。

既定では、 **/opt:ref による**がリンカーによって有効になっていない限り **/OPT:NOREF**または[/debug](../../build/reference/debug-generate-debug-info.md)を指定します。 プログラムで参照されていない Comdat を変更この既定値を上書きするには、次のように指定します。 **/OPT:NOREF**です。 使用することができます、 [/include](../../build/reference/include-force-symbol-references.md)シンボルの特定の削除のオーバーライド オプションを指定します。

場合[/debug](../../build/reference/debug-generate-debug-info.md)が指定されているの既定の **/opt**は**NOREF**、され、イメージのすべての機能が保持されます。 この既定の動作をオーバーライドし、デバッグ ビルドの最適化するには指定 **/opt:ref による**です。 これは、実行可能ファイルのサイズを減らすことができ、デバッグの場合でも有効な最適化を構築することができます。 指定することをお勧め **/OPT:NOICF**デバッグ関数ビルドの保持と同じにします。 これにより、スタック トレースを読み取って、圧縮された関数にブレークポイントを設定しやすくなります。

**ICF**\[**=**_イテレーション_] &#124; **NOICF**

使用して**ICF**\[**=**_イテレーション_] を同一の COMDAT の圧縮を実行します。 リンカー出力から余分な COMDAT シンボルを削除できます。 省略可能な*イテレーション*パラメーターは、重複部分のシンボルを走査する回数を指定します。 既定のイテレーションの数は 1 です。 イテレーションの回数を増やすと、前回のイテレーションで圧縮されなかった重複が検出されることがあります。

既定では、 **/OPT:ICF**がリンカーによって有効になっていない限り **/OPT:NOICF**または[/debug](../../build/reference/debug-generate-debug-info.md)を指定します。 この既定の動作をオーバーライドし、プログラムで折りたたまれているから Comdat を防止するのには、指定 **/OPT:NOICF**です。

デバッグ ビルドである必要があります明示的に指定する **/OPT:ICF** COMDAT の圧縮を有効にします。 ただし、ため **/OPT:ICF**同一のデータまたは関数をマージすることができます、スタック トレースに表示される関数名を変更することができます。 できない原因となる特定の関数にブレークポイントを設定するか、デバッガーの一部のデータを検査して、予期しない関数を考慮することができますとシングル ステップ、コードを使用します。 コードの動作は同じですがデバッガー プレゼンテーションは不思議なことができます。 そのため、おしないで使用する **/OPT:ICF**デバッグ ビルドでより小さなコードの利点がこうした欠点を上回らない限り、します。

> [!NOTE]
> **/OPT:ICF**同じアドレスを別の関数または読み取り専用のデータ メンバーに割り当てられる可能性があります (つまり、 **const**変数を使用して、コンパイル時に **/Gy**)、関数または読み取り専用データ メンバーの一意のアドレスに依存するプログラムを壊すことできます。 詳細については、「[/Gy (関数レベルのリンクの有効化)](../../build/reference/gy-enable-function-level-linking.md)」を参照してください。

**LBR** &AMP;#124; **NOLBR**

**/OPT:LBR**と **/OPT:NOLBR**オプションは、ARM バイナリのみに適用します。 特定の ARM プロセッサの分岐命令の範囲が限られているため、リンカーは、範囲外のアドレスへのジャンプを検出すると、分岐命令の終点アドレスを、実際の終点を対象とする分岐命令を含むコード "アイランド" のアドレスに置き換えます。 使用することができます **/OPT:LBR**長い分岐命令の検出と、コード全体のサイズを最小限に抑える中間コード アイランドの配置を最適化します。 **/OPT:NOLBR**が検出されると、最適化を行わずに長い分岐命令のコード アイランドを生成するようにリンカーに指示します。

既定では、 **/OPT:LBR**インクリメンタル リンクが有効でない場合に、オプションが設定されています。 非インクリメンタル リンクですがない時間の長い分岐命令の最適化をする場合、指定 **/OPT:NOLBR**です。 **/OPT:LBR**オプションは、インクリメンタル リンクを無効になります。

## <a name="remarks"></a>コメント

リンカーが既定で使用すると、コマンドラインで、 **/opt:ref による、ICF、LBR**です。 場合 **/debug**を指定すると、既定値は **/OPT:NOREF、NOICR、NOLBR**です。

**/Opt**最適化処理は通常、イメージ サイズを小さくと、プログラムの実行速度を向上します。 これらの機能強化は、リテール ビルドの既定で有効になっているため、大規模なプログラムで大幅なで指定できます。

リンカー最適化前払い、余分な時間がかかりが最適化されたコードでは、小さいデバッグ情報を処理し、pdb ファイルに書き込むためにはさらに多くの時間の節約と、リンカーが少ないの再配置を修正し小さいの最終的なイメージを作成する時点も保存されます。 最適化を有効にすると、それと損なわれる可能性リンク時間が短く全体的に見て、分析で小規模の追加コスト可能性がある複数の削減量はリンカーが小さいバイナリを通過する時間のオフセットします。

**/Opt**引数が同時に指定する、コンマで区切っています。 たとえばの代わりに **/opt:ref による/OPT:NOICF**を指定できます **/opt:ref による、NOICF**です。

使用することができます、 [/verbose](../../build/reference/verbose-print-progress-messages.md)リンカー オプションによって削除された関数を表示する **/opt:ref による**およびによって圧縮された関数 **/OPT:ICF**です。

**/Opt**引数を使用して作成したプロジェクトの多くは、設定、**新しいプロジェクト**で Visual Studio IDE、ダイアログ、通常、デバッグ用の別の値を持って構成とリリース構成します。 プロジェクトでこれらのリンカー オプションの値が設定されていない場合は、プロジェクトの既定値は、コマンドラインで、リンカーによって使用される既定値と異なる場合を取得可能性があります。

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:ICF リンカー オプションまたは OPT:REF リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **最適化**プロパティ ページ。

1. 次のいずれかのプロパティを変更します。

   - **COMDAT の圧縮**

   - **参照**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:LBR リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して**追加オプション**:

   `/opt:lbr` または `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
- [リンカー オプション](../../build/reference/linker-options.md)
