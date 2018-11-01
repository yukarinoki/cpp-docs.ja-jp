---
title: /SOURCELINK (PDB に含める Sourcelink ファイル)
ms.date: 08/20/2018
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: 5c742a37803f450aa6084c862800583f70bcedde
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480991"
---
# <a name="sourcelink-include-sourcelink-file-in-pdb"></a>/SOURCELINK (PDB に含める Sourcelink ファイル)

リンカーによって生成される PDB ファイルに含める SourceLink 構成ファイルを指定します。

## <a name="syntax"></a>構文

> **/SOURCELINK:**_ファイル名_

## <a name="arguments"></a>引数

*ファイル名*<br/>
JSON 形式の構成ファイルの Url へのローカル ファイル パスの単純なマッピングを含むソース ファイルを取得できる、デバッガーによって表示を指定します。 このファイルの形式の詳細については、次を参照してください。[ソース リンクの JSON スキーマ](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema)します。

## <a name="remarks"></a>Remarks

SourceLink は、ソースのバイナリのデバッグを提供するために依存しない言語とソース管理システムです。 以降では、Visual Studio 2017 バージョン 15.8 ネイティブの C++ バイナリでは、SourceLink はサポートされます。 SourceLink の概要については、次を参照してください。[ソース リンク](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md)します。 プロジェクトで SourceLink を使用する方法と、プロジェクトの一部として、SourceLink ファイルを生成する方法については、次を参照してください。[を使用して SourceLink](https://github.com/dotnet/sourcelink#using-sourcelink)します。

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Visual Studio で/SOURCELINK リンカー オプションを設定するには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. **追加オプション**ボックスで、追加 **/SOURCELINK:**_filename_選び、 **[ok]** または**適用**、変更を保存します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- このオプションでは、同等のプログラムはありません。

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
