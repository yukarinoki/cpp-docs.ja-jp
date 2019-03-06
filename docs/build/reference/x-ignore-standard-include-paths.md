---
title: /X (標準インクルード パスの無視)
ms.date: 11/04/2016
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
ms.openlocfilehash: 615a53a7ad29527187072c3131f551a76bd18969
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421372"
---
# <a name="x-ignore-standard-include-paths"></a>/X (標準インクルード パスの無視)

コンパイラが、PATH および INCLUDE 環境変数で指定されたディレクトリのインクルード ファイルを検索するを防ぎます。

## <a name="syntax"></a>構文

```
/X
```

## <a name="remarks"></a>Remarks

このオプションを使用することができます、 [/I (追加インクルード ディレクトリ)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**プリプロセッサ**プロパティ ページ。

1. 変更、**標準インクルード パスの無視**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>

## <a name="example"></a>例

次のコマンドで`/X`PATH および INCLUDE 環境変数で指定された位置を無視するようにコンパイラに指示し、`/I`で検索するディレクトリを指定しますファイルを含めます。

```
CL /X /I \ALT\INCLUDE MAIN.C
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
