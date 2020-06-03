---
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
ms.openlocfilehash: e0d23004c7b710f51065db52410fbb15b7cca040
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320490"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (同一文字列の削除)

コンパイラが、実行中にプログラム イメージとメモリ内に同一の文字列のコピーを作成できるようにします。 これは、より小さなプログラムを作成できる*文字列プーリング*と呼ばれる最適化です。

## <a name="syntax"></a>構文

```
/GF
```

## <a name="remarks"></a>解説

**/GF**を使用すると、オペレーティング システムはメモリの文字列部分をスワップせず、イメージ ファイルから文字列を読み取ることができます。

**/GF**は文字列を読み取り専用としてプールします。 **/GF**で文字列を変更しようとすると、アプリケーション エラーが発生します。

文字列プーリングでは、複数のバッファーへの複数のポインターとして意図されていたものを、単一のバッファーへの複数のポインターにできます。 次のコードでは、`s`同`t`じ文字列で初期化されます。 文字列プーリングによって、これらのオブジェクトは同じメモリを指します。

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> エディット コンティニュに使用される[/ZI](z7-zi-zi-debug-information-format.md)オプションは **、/GF**オプションを自動的に設定します。

> [!NOTE]
> **/GF**コンパイラ オプションは、一意の文字列ごとにアドレス指定可能なセクションを作成します。 デフォルトでは、オブジェクトファイルには最大65,536のアドレス可能なセクションを含めることができます。 プログラムに含まれる文字列が 65,536 個を超える場合は[、/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)コンパイラ オプションを使用して、より多くのセクションを作成します。

**/GF**は[、/O1](o1-o2-minimize-size-maximize-speed.md)または[/O2](o1-o2-minimize-size-maximize-speed.md)が使用されている場合に有効です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [**コード生成**] プロパティ ページをクリックします。

1. **[文字列プールを有効にする]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
