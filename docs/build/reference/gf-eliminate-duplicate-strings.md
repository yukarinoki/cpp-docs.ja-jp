---
description: 詳細情報:/GF (重複する文字列の削除)
title: /GF (同一文字列の削除)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 65c8cca610b9e01cf49939c2074a698b00c6e338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191941"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (同一文字列の削除)

実行中に、コンパイラがプログラムイメージとメモリに同一の文字列のコピーを1つ作成できるようにします。 これは、小さなプログラムを作成できる *文字列プール* と呼ばれる最適化です。

## <a name="syntax"></a>構文

```
/GF
```

## <a name="remarks"></a>解説

**/Gf** を使用する場合、オペレーティングシステムはメモリの文字列部分をスワップせず、イメージファイルから文字列を読み取ることができます。

**/Gf** プール文字列は読み取り専用になります。 **/Gf** で文字列を変更しようとすると、アプリケーションエラーが発生します。

文字列プーリングでは、複数のバッファーへの複数のポインターとして、1つのバッファーへの複数のポインターとして意図されたものを使用できます。 次のコードで `s` は、と `t` が同じ文字列で初期化されます。 文字列プーリングは、同じメモリを指すようにします。

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> [/Zi](z7-zi-zi-debug-information-format.md)オプションは、エディットコンティニュに使用され、自動的に **/gf** オプションを設定します。

> [!NOTE]
> **/Gf** コンパイラオプションは、一意の文字列ごとにアドレス指定可能なセクションを作成します。 既定では、オブジェクトファイルには、最大65536のアドレス指定可能なセクションを含めることができます。 プログラムに65536個を超える文字列が含まれている場合は、 [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) コンパイラオプションを使用して、さらにセクションを作成します。

[/O1](o1-o2-minimize-size-maximize-speed.md)または [/O2](o1-o2-minimize-size-maximize-speed.md)が使用されている場合、 **/gf** が有効になります。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **コード生成** ] プロパティページをクリックします。

1. " **文字列プールを有効にする** " プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
