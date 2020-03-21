---
title: 'ブラウザー情報ファイルのビルド : 概要'
ms.date: 05/06/2019
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: 94cb5865e56e12f51ef4a8598a5df3fcbe69fa0f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078360"
---
# <a name="building-browse-information-files-overview"></a>ブラウザー情報ファイルのビルド : 概要

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

シンボル参照の参照情報を作成するために、コンパイラはプロジェクト内の各ソースファイルに対して .sbr ファイルを作成し、BSCMAKE を使用します。EXE は、.sbr ファイルを1つの .bsc ファイルに連結します。

.Sbr ファイルと .bsc ファイルを生成するには時間がかかります。そのため、Visual Studio では、これらの関数が既定でオフになります。 現在の情報を参照するには、参照オプションをオンにしてから、プロジェクトを再度ビルドする必要があります。

[/Fr](fr-fr-create-dot-sbr-file.md)または[/fr](fr-fr-create-dot-sbr-file.md)を使用して、.sbr ファイルを作成するようにコンパイラに指示します。 .Bsc ファイルを作成するには、コマンドラインから[BSCMAKE](bscmake-command-line.md)を呼び出すことができます。 コマンドラインから BSCMAKE を使用すると、ブラウザー情報ファイルの操作をより細かく制御できます。 詳細については、「 [BSCMAKE リファレンス](bscmake-reference.md)」を参照してください。

> [!TIP]
>  .Sbr ファイルの生成を有効にすることはできますが、.bsc ファイルの生成は無効のままにしておきます。 これにより、高速ビルドが可能になりますが、.bsc ファイルの生成を有効にし、プロジェクトをビルドすることで、新しい .bsc ファイルをすばやく作成することもできます。

.Bsc ファイルのサイズを小さくすることで、.bsc ファイルをビルドするために必要な時間、メモリ、およびディスク領域を減らすことができます。

開発環境でブラウザーファイルをビルドする方法の詳細については、「 [[全般] プロパティページ (プロジェクト)](general-property-page-project.md) 」を参照してください。

### <a name="to-create-a-smaller-bsc-file"></a>より小さな .bsc ファイルを作成するには

1. 参照情報ファイルから情報を除外するには、 [BSCMAKE のコマンドラインオプション](bscmake-options.md)を使用します。

1. コンパイルまたはアセンブルするときに、1つまたは複数の .sbr ファイルでローカルシンボルを省略します。

1. 現在のデバッグ段階で必要な情報がオブジェクトファイルに含まれていない場合は、ブラウザー情報ファイルを再構築するときに、BSCMAKE コマンドからその .sbr ファイルを省略します。

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>複数のプロジェクトの参照情報を1つのブラウザーファイル (.bsc) に結合するには

1. .Bsc ファイルがプロジェクトレベルでビルドされないようにするか、または/n スイッチを使用して .sbr ファイルが切り捨てられないようにします。

1. すべてのプロジェクトがビルドされたら、すべての .sbr ファイルを入力として BSCMAKE を実行します。 ワイルドカードを使用できます。 たとえば、プロジェクトディレクトリが "C:\ x"、"C:\ Y"、および "C:\ Z" で .sbr ファイルがある場合、それらをすべて1つの .bsc ファイルに結合するには、BSCMAKE c:\ X\\\*を使用します。この場合は、\\\*. .sbr c:\\\\*。

## <a name="see-also"></a>参照

[追加の MSVC ビルド ツール](c-cpp-build-tools.md)<br/>
[BSCMAKE リファレンス](bscmake-reference.md)
