---
description: '詳細については、/Zc: forScope (for ループスコープの強制準拠) に関するページを参照してください。'
title: /Zc:forScope (for ループのスコープの強制準拠)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: 7124bba6608facfea546974cfa40ef9556ff713a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114664"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (for ループのスコープの強制準拠)

Microsoft の拡張機能 ( [/Ze](../../cpp/for-statement-cpp.md) ) の[for](za-ze-disable-language-extensions.md)ループの標準 C++ 動作を実装するために使用します。

## <a name="syntax"></a>構文

> **/Zc: forScope**[ **-** ]

## <a name="remarks"></a>解説

標準の動作では、ループの初期化子がループの後にスコープ外に出るようにし **`for`** **`for`** ます。 **/Zc: forScope-** および [/ze](za-ze-disable-language-extensions.md)では、 **`for`** ループの初期化子は、ローカルスコープが終了するまでスコープ内に残ります。

**/Zc: forScope** オプションは既定でオンになっています。 **/Zc: forScope** は、 [/permissive-](permissive-standards-conformance.md) オプションが指定されている場合、影響を受けません。

**/Zc:forScope-** オプションは非推奨とされます。今後のバージョンからは削除されます。 **/Zc:forScope-** を使うと、廃止予定の警告 D9035 が表示されます。

次のコードは **/Ze** ではコンパイルされますが、 **/Za** ではコンパイルされません。

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

**/Zc:forScope-** を使う場合、以前のスコープで行った宣言によって変数がスコープ内にあるときに、警告 C4288 (既定ではオフ) が表示されます。 これを示すために、サンプル コードから `//` の文字を削除して `int i`を宣言します。

**/Zc:forScope** の実行時の動作は、 [conform](../../preprocessor/conform.md) プラグマを使って変更できます。

既存の .pch ファイルがあるプロジェクトで **/Zc:forScope-** を使う場合、警告が表示され、 **/Zc:forScope-** は無視され、既存の .pch ファイルを使ってコンパイルが継続されます。 新しい .pch ファイルを生成する場合は、 [/yc (プリコンパイル済みヘッダーファイルの作成)](yc-create-precompiled-header-file.md)を使用します。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **言語**] プロパティページを選択します。

1. **[for ループ スコープの強制準拠]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>
[/Za、/Ze (言語拡張機能の無効化)](za-ze-disable-language-extensions.md)<br/>
