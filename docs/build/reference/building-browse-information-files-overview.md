---
title: 'ブラウザー情報ファイルのビルド : 概要'
ms.date: 05/06/2019
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: ffacb7aaf9ac1f7ad6fc4cf12ab479099dc57725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320670"
---
# <a name="building-browse-information-files-overview"></a>ブラウザー情報ファイルのビルド : 概要

> [!WARNING]
> BSCMAKE は、現在も Visual Studio と共にインストールされていますが、IDE では使用されなくなりました。 Visual Studio 2008 以降、ブラウザーとシンボルの情報は、ソリューション フォルダー内の SQL Server の .sdf ファイルに自動的に格納されます。

シンボル参照の参照情報を作成するために、コンパイラはプロジェクト内の各ソース ファイルに対して .sbr ファイルを作成し、次に BSCMAKE を作成します。EXE は、.sbr ファイルを 1 つの .bsc ファイルに連結します。

.sbr ファイルと .bsc ファイルの生成には時間がかかるため、Visual Studio ではこれらの関数が既定でオフになります。 現在の情報を参照する場合は、参照オプションをオンにして、プロジェクトを再度ビルドする必要があります。

[/FR](fr-fr-create-dot-sbr-file.md)または[/Fr](fr-fr-create-dot-sbr-file.md)を使用して、.sbr ファイルを作成するようにコンパイラに指示します。 .bsc ファイルを作成するには、コマンド ラインから[BSCMAKE を](bscmake-command-line.md)呼び出します。 コマンド ラインから BSCMAKE を使用すると、参照情報ファイルの操作をより正確に制御できます。 詳細については[、「BSCMAKE リファレンス」](bscmake-reference.md)を参照してください。

> [!TIP]
> .sbr ファイルの生成は有効にできますが、.bsc ファイルの生成はオフのままにしておきます。 これにより、高速ビルドが可能になりますが、.bsc ファイルの生成を有効にしてプロジェクトをビルドすることで、新しい .bsc ファイルを迅速に作成することもできます。

.bsc ファイルのサイズを小さくすることによって、.bsc ファイルの作成に必要な時間、メモリ、およびディスク領域を削減できます。

開発環境でブラウザー ファイルをビルドする方法については、「[一般プロパティ ページ (Project)」](general-property-page-project.md)を参照してください。

### <a name="to-create-a-smaller-bsc-file"></a>より小さい .bsc ファイルを作成するには

1. [BSCMAKE コマンド ライン オプション](bscmake-options.md)を使用して、参照情報ファイルから情報を除外します。

1. コンパイルまたはアセンブルの際に、1 つ以上の .sbr ファイルでローカル シンボルを省略します。

1. オブジェクト ファイルにデバッグの現在の段階に必要な情報が含まれていない場合は、参照情報ファイルを再構築するときに、BSCMAKE コマンドから .sbr ファイルを省略します。

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>複数のプロジェクトの参照情報を 1 つのブラウザー ファイル (.bsc) に結合するには

1. プロジェクト レベルで .bsc ファイルをビルドしないか、/n スイッチを使用して .sbr ファイルが切り捨てられないようにします。

1. すべてのプロジェクトがビルドされたら、すべての .sbr ファイルを入力として BSCMAKE を実行します。 ワイルドカードを使用できます。 たとえば、プロジェクト ディレクトリ C:\X、C:\Y、C:\Z と .sbr ファイルを含む C:\\Z があり、それらを 1 つの .bsc ファイルに結合\\\*する場合は、BSCMAKE\\\*C:\X .sbr C:\Y .sbr C:whatever_directory\Y .sbr C:\Z\\\*.sbr/結合.bsc を使用して、結合された .bsc ファイルを作成します。

## <a name="see-also"></a>関連項目

[その他の MSVC ビルド ツール](c-cpp-build-tools.md)<br/>
[BSCMAKE リファレンス](bscmake-reference.md)
