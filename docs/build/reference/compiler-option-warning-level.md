---
title: /w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//we、/wo、/Wv、/WX (警告レベル)
ms.date: 01/31/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.openlocfilehash: 4842e845013bf69a7bc033ba7b6abf5ecc7d5079
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441744"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、//we、/wo、/Wv、/WX (警告レベル)

指定したコンパイルの警告の生成方法を指定します。

## <a name="syntax"></a>構文

> **/w**
>  **/W0**
>  **/W1**
>  **/W2**
>  **/W3** 
>  **/W4**
>  **/wall**
>  **/Wv**\[**:**_バージョン_] **/WX**
>  **/w1**_警告_
>  **/w2** _警告_
>  **/w3**_警告_
>  **/w4**_警告_
>  **/wd**_警告_
>  **/we**_警告_
>  **/wo**_警告_

## <a name="remarks"></a>Remarks

警告のオプションは、どのコンパイラの警告を表示し、全体のコンパイルの警告の動作を指定します。

警告のオプションと関連する引数は、次の表のとおりです。

|オプション|説明|
------------|-----------------|
|**/w**|すべてのコンパイラ警告を抑制します。|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|コンパイラによって生成される警告のレベルを指定します。 有効な警告レベルを 0 ~ 4 の範囲。<br />**/W0**すべての警告を抑制します。 これに相当 **/w**します。<br />**/W1**レベル 1 (重大) の警告が表示されます。 **/W1**コマンド ライン コンパイラで既定の設定です。<br />**/W2**レベル 1 およびレベル 2 (重要) の警告を表示します。<br />**/W3**レベル 1、レベル 2 とレベル 3 (実稼働品質) の警告が表示されます。 **/W3** IDE の既定の設定です。<br />**/W4**レベルの既定でオフになっていない 4 の (情報) 警告すべてとレベル 1、レベル 2 とレベル 3 の警告が表示されます。 このオプションを使用して、lint のような警告を提供することをお勧めします。 新しいプロジェクトの場合を使用する最適な場合があります **/W4**すべてのコンパイルでこれにより、最小限の考えられる検索ハード コード障害を検出します。|
|**/Wall**|によって表示されるすべての警告が表示されます **/W4**とその他のすべての警告を **/W4**は含まれません: 既定で無効にする警告など。 詳細については、次を参照してください。[コンパイラの警告を、既定でオフ](../../preprocessor/compiler-warnings-that-are-off-by-default.md)します。|
|**/Wv**\[**:**_version_]|コンパイラのバージョンで導入された警告のみを表示します*バージョン*以前のバージョン。 コンパイラの新しいバージョンに移行する場合は、コードでの新しい警告を抑制して、それらを修正する間に、既存のビルド プロセスを維持するために、このオプションを使用することができます。 省略可能なパラメーター*バージョン*形式の*nn*[.*mm*[.*以下*]、 *nn* 、メジャー バージョン番号は、 *mm*は省略可能なマイナー バージョン番号、および*以下*は省略可能なビルドの数ですコンパイラ。 たとえば、使用して */Wv:17*またはそれ以前、Visual Studio 2012 (つまり、17 のメジャー バージョン番号を持つコンパイラの任意のバージョンなど) に導入された警告を表示する、Visual Studio 2013 (メジャー バージョンで導入された警告を抑制するには18) 以降。 既定では、 **/Wv**使用して、現在のコンパイラ バージョン番号、および警告が表示されないが抑制されます。 コンパイラのバージョンでどの警告の抑制については、次を参照してください。[コンパイラのバージョンによるコンパイラの警告](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md)します。|
|**/WX**|コンパイラ警告をすべてエラーとして扱います。 新しいプロジェクトの場合を使用する最適な場合があります **/WX**すべてのコンパイルですべての警告を解決するにより、最小限の考えられる検索ハード コード障害を検出します。<br /><br /> リンカーにも、 **/WX**オプション。 詳細については、「[/WX (リンカー警告をエラーとして扱う)](../../build/reference/wx-treat-linker-warnings-as-errors.md)」を参照してください。|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|指定された警告の数の警告レベルを設定_nnnn_します。 これにより、特定の警告レベルが設定されている場合、その警告のコンパイラの動作を変更できます。 これらのオプションは、既定の Visual Studio によって提供されるものではなく、警告、独自のコーディング標準を適用するのに他の警告のオプションと組み合わせて使用できます。<br /><br /> たとえば、 **/w34326** C4326 レベル 1 ではなく、レベル 3 警告として生成されるとします。 両方を使用してコンパイルする場合、 **/w34326**オプションと **/W2**オプション、警告 C4326 は生成されません。|
|**/wd**_nnnn_|指定されているコンパイラ警告_nnnn_します。<br /><br /> たとえば、 **/wd4326**コンパイラの警告 C4326 を抑制します。|
|**/we**_nnnn_|指定されているコンパイラの警告扱います_nnnn_をエラーとして。<br /><br /> たとえば、 **/we4326**警告番号をコンパイラによってエラーとして扱う C4326 をによりします。|
|**/wo**_nnnn_|指定された、コンパイラの警告がレポート_nnnn_ 1 回だけです。<br /><br /> たとえば、 **/wo4326** C4326 1 回だけに報告されることを警告の原因が初めて検出された、コンパイラによって。|

使用してプリコンパイル済みヘッダーを作成するときに警告のオプションのいずれかを使用する場合、 [/Yc](../../build/reference/yc-create-precompiled-header-file.md)オプションを使用してプリコンパイル済みヘッダーの使用はすべて、 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)オプションは、それら同じ警告のオプションを有効にします。もう一度です。 警告のオプションをコマンドラインで別の警告オプションを使用して、プリコンパイル済みヘッダーの設定をオーバーライドできます。

使用することができます、 [#pragma warning](../../preprocessor/warning.md)は警告のレベルを制御するディレクティブが特定のソース ファイルのコンパイル時に報告します。

ソース コードの警告プラグマ ディレクティブは影響を受けることは、 **/w**オプション。

[エラーに関するドキュメントをビルド](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)警告および警告レベルについて説明し、なぜ特定のステートメントがコンパイルされません意図したとすることを示します。

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 設定する、 **/W0**、 **/W1**、 **/W2**、 **/W3**、 **/W4**、 **/wall**m **/Wv**、 **/WX**または **/WX-** オプションの選択、**構成プロパティ** > **C/C++** > **全般**プロパティ ページ。

   - 設定する、 **/W0**、 **/W1**、 **/W2**、 **/W3**、 **/W4**、または **/wall**オプションの変更、**警告レベル**プロパティ。

   - 設定する、 **/WX**または **/WX-** オプション、変更、**警告をエラーとして扱う**プロパティ。

   - バージョンを設定する、 **/Wv**オプションで、コンパイラのバージョン番号を入力、**警告バージョン**プロパティ。

1. 設定する、 **/wd**または **/we**オプションの選択、**構成プロパティ** > **C/C++**  >  **高度な**プロパティ ページ。

   - 設定する、 **/wd**オプションを選択し、**特定の警告を無効にする**プロパティは、ドロップ ダウン コントロールし、**編集**します。 編集ボックスに、**特定の警告を無効にする**ダイアログ ボックスで、警告番号を入力します。 1 つ以上の警告を入力するには、セミコロンを使用して、値を区切る (**;**)。 たとえば、C4001 と C4010 の両方を無効にする次のように入力します。 **4001; 4010**します。 選択**OK**に戻って変更を保存する、**プロパティ ページ**ダイアログ。

   - 設定する、 **/we**オプションを選択、**特定の警告をエラーとして扱う**プロパティは、ドロップ ダウン コントロールし、**編集**します。 編集ボックスに、**特定の警告をエラーとして扱う**ダイアログ ボックスで、警告番号を入力します。 1 つ以上の警告を入力するには、セミコロンを使用して、値を区切る (**;**)。 たとえば、C4001 と C4010 の両方をエラーとして扱う、次のように入力します。 **4001; 4010**します。 選択**OK**に戻って変更を保存する、**プロパティ ページ**ダイアログ。

1. 設定する、 **/wo**オプションを選択し、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。 コンパイラ オプションを入力して、**追加オプション**ボックス。

1. **OK** を選択して変更を保存してください。

### <a name="to-set-the-compiler-option-programmatically"></a>コンパイラ オプションをプログラムで設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>」、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>」、および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
