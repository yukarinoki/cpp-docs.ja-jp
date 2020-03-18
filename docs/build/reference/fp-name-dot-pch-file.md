---
title: /Fp (pch ファイルの名前 &period;)
description: /Fp コンパイラオプションを使用して、プリコンパイル済みヘッダーファイル名を指定します。
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: d62c5bd9fc7920c0a2a5530879680fad2a01d39a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439780"
---
# <a name="fp-name-periodpch-file"></a>/Fp (pch ファイルの名前 &period;)

既定のパス名を使用するのではなく、プリコンパイル済みヘッダーのパス名を提供します。

## <a name="syntax"></a>構文

> **/Fp**<em>パス名</em>

## <a name="remarks"></a>コメント

[/Yc (プリコンパイル済みヘッダーファイルの作成)](yc-create-precompiled-header-file.md)または[/yu (](yu-use-precompiled-header-file.md)プリコンパイル済みヘッダーファイルの使用) で **/fp**オプションを使用して、プリコンパイル済みヘッダー (PCH) ファイルのパスとファイル名を指定します。 既定では、 **/yc**オプションは、ソースファイルのベース名と*pch*拡張子を使用して pch ファイル名を作成します。

拡張機能を*パス名*の一部として指定しない場合、 *pch*の拡張子が使用されます。 *パス*名の末尾にスラッシュ ( **/** ) を使用してディレクトリ名を指定した場合、既定のファイル名は vc*バージョン*0. .pch になります。ここで、 *version*は Visual Studio ツールセットのメジャーバージョンです。 このディレクトリが存在している必要があります。存在しない場合、エラー C1083 が生成されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **構成プロパティ** > **C/C++**  > **プリコンパイル済みヘッダー**  プロパティページを開きます。

1. **プリコンパイル済みヘッダーの出力ファイル**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>) をご覧ください。

## <a name="examples"></a>例

プログラムのデバッグビルド用にプリコンパイル済みヘッダーファイルの名前付きバージョンを個別に作成するには、次のようなコマンドを指定します。

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

次のコマンドは、MYPCH .pch という名前のプリコンパイル済みヘッダーファイルを使用することを指定します。 コンパイラは、myapp.exe のソースコードを MYAPP の末尾からプリコンパイルし、プリコンパイル済みコードを MYPCH .pch に配置します。 次に、MYPCH の内容を使用し、残りの PROG をコンパイルして .obj ファイルを作成します。 この例の出力は、PROG という名前のファイルです。

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>参照

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
