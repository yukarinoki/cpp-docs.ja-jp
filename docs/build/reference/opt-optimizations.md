---
title: /OPT (最適化)
ms.date: 05/18/2018
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
ms.openlocfilehash: 874c4b974348d1bef8c8c3837f46c1c27d6d304b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215193"
---
# <a name="opt-optimizations"></a>/OPT (最適化)

LINK がビルド時に実行する最適化を制御します。

## <a name="syntax"></a>構文

> **/OPT:**{**REF**  |  **NOREF**} \
> **/Opt:**{**ICF**[ **=** _イテレーション_] |**Noicf**}\
> **/OPT:**{**LBR**  |  **NOLBR**}

## <a name="arguments"></a>引数

**参照**&#124; **noref**

**/Opt: REF**は、参照されない関数とデータを排除します。**/Opt: NOREF**は、参照されない関数とデータを保持します。

/OPT: REF が有効な場合、リンクを使用すると、参照されていないパッケージ関数とデータ ( *comdat*と呼ばれる) が削除されます。 この最適化は、中間 COMDAT 除去として知られています。 **/Opt: REF**オプションを指定すると、インクリメンタルリンクも無効になります。

クラス宣言内で定義されているインライン関数とメンバー関数は、常に Comdat です。 オブジェクトファイル内のすべての関数は、 [/gy](gy-enable-function-level-linking.md)オプションを使用してコンパイルされた場合、comdat に作成されます。 データを Comdat に配置するには **`const`** 、を使用してデータを宣言する必要があり `__declspec(selectany)` ます。 削除または折りたたみの対象となるデータを指定する方法については、「 [selectany](../../cpp/selectany.md)」を参照してください。

既定では、/opt: **NOREF**または[/debug](debug-generate-debug-info.md)が指定されていない限り、 **/opt: REF**はリンカーによって有効になります。 この既定値をオーバーライドし、プログラムに参照されていない Comdat を保持するには、 **/opt: NOREF**を指定します。 [/INCLUDE](include-force-symbol-references.md)オプションを使用すると、特定のシンボルの削除を上書きできます。

[/Debug](debug-generate-debug-info.md)を指定すると、 **/opt**の既定値は**noref**になり、すべての関数がイメージに保持されます。 この既定値をオーバーライドし、デバッグビルドを最適化するには、 **/opt: REF**を指定します。 これにより、実行可能ファイルのサイズを小さくすることができ、デバッグビルドでも便利な最適化を行うことができます。 デバッグビルドで同一の関数を保持するには、 **/opt: NOICF**も指定することをお勧めします。 これにより、スタック トレースを読み取って、圧縮された関数にブレークポイントを設定しやすくなります。

**ICF** \[ ICF **=**_イテレーション_]&#124; **Noicf**

**ICF** \[ **=** 同じ COMDAT フォールドを実行するには、ICF_イテレーション_を使用します。 リンカー出力から余分な COMDAT シンボルを削除できます。 *省略可能*な iteration パラメーターは、シンボルが重複していないかどうかを走査する回数を指定します。 既定のイテレーション数は1です。 イテレーションの回数を増やすと、前回のイテレーションで圧縮されなかった重複が検出されることがあります。

既定では、/opt: **NOICF**または[/debug](debug-generate-debug-info.md)が指定されていない限り、 **/opt: ICF**がリンカーによって有効になります。 この既定値をオーバーライドして、プログラムで Comdat が折りたたまれないようにするには、 **/opt: NOICF**を指定します。

デバッグビルドでは、COMDAT 圧縮を有効にするために **/opt: ICF**を明示的に指定する必要があります。 ただし、 **/opt: ICF**は同一のデータまたは関数をマージできるため、スタックトレースに表示される関数名を変更できます。 また、特定の関数にブレークポイントを設定したり、デバッガーでデータを調べたりすることができなくなります。また、コードをシングルステップ実行するときに、予期しない関数を使用することもできます。 コードの動作は同じですが、デバッガーのプレゼンテーションが非常にわかりにくい場合があります。 そのため、小さなコードの利点がこれらの欠点を上回る場合を除き、デバッグビルドで **/opt: ICF**を使用することはお勧めしません。

> [!NOTE]
> **/Opt: ICF**により、同じアドレスが異なる関数または読み取り専用データメンバー (つまり、/gy を使用してコンパイルされた場合は変数) に割り当てられる可能性があるため **`const`** 、関数または読み取り専用データメンバーの一意のアドレスに依存するプログラムを中断できます。 **/Gy** 詳細については、「[/Gy (関数レベルのリンクの有効化)](gy-enable-function-level-linking.md)」を参照してください。

**Lbr** &#124; **nolbr**

**/Opt: LBR**オプションと **/OPT: nolbr**オプションは ARM バイナリにのみ適用されます。 特定の ARM プロセッサの分岐命令の範囲が限られているため、リンカーが範囲外のアドレスへのジャンプを検出すると、分岐命令の宛先アドレスが、実際の宛先をターゲットとする分岐命令を含むコード "アイランド" のアドレスに置き換えられます。 **/Opt: LBR**を使用すると、長い分岐命令の検出と中間コードアイランドの配置を最適化して、コード全体のサイズを最小限に抑えることができます。 **/Opt: NOLBR**は、長い分岐命令が検出されたときに、最適化を行わずにコードアイランドを生成するようにリンカーに指示します。

既定では、インクリメンタルリンクが有効になっていない場合、 **/opt: LBR**オプションが設定されます。 インクリメンタルリンクを必要としないが、長い分岐の最適化を使用しない場合は、 **/opt: NOLBR**を指定します。 **/Opt: LBR**オプションを指定すると、インクリメンタルリンクが無効になります。

## <a name="remarks"></a>解説

コマンドラインで使用する場合、リンカーは既定で **/opt: REF、ICF、LBR**に設定されます。 **/Debug**が指定されている場合、既定値は **/OPT: NOREF、NOICF、nolbr**です。

**/Opt**の最適化では、通常、イメージのサイズが小さくなり、プログラムの速度が向上します。 これらの機能強化は、大規模なプログラムでは非常に大きくなる可能性があります。そのため、製品版ビルドでは既定で有効になります。

リンカーの最適化では、前に余分な時間がかかりますが、最適化されたコードでは、リンカーの再配置が少なく、最終的なイメージが小さくなるまでの時間を節約できます。また、デバッグ情報が少なくなり、PDB を処理して書き込むこともできます。 最適化が有効になっていると、リンク時間が短縮される可能性があります。これは、より小さなバイナリに対してリンカーが渡す時間の短縮によって、分析のコストが大幅に増加する可能性があるためです。

**/Opt**引数は、コンマで区切って指定できます。 たとえば、 **/opt: ref/opt: noicf**の代わりに、 **/opt: REF, noicf**を指定できます。

[/Verbose](verbose-print-progress-messages.md)リンカーオプションを使用すると、 **/opt: REF**によって削除された関数と、 **/opt: ICF**によって折りたたまれた関数を確認できます。

**/Opt**引数は、多くの場合、VISUAL Studio IDE の [**新しいプロジェクト**] ダイアログボックスを使用して作成されたプロジェクトに対して設定され、デバッグ構成とリリース構成の値は異なります。 プロジェクトでこれらのリンカーオプションに値が設定されていない場合、プロジェクトの既定値を取得できます。これは、コマンドラインでリンカーによって使用される既定値とは異なる場合があります。

### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:ICF リンカー オプションまたは OPT:REF リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**の  >  **最適化**] プロパティページを選択します。

1. 次のいずれかのプロパティを変更します。

   - **[COMDAT の圧縮]**

   - **参照**

### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で OPT:LBR リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **リンカー**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] でオプションを入力します。

   `/opt:lbr` または `/opt:nolbr`

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
