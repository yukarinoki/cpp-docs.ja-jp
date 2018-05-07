---
title: 指定するカスタム ビルド ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets
- VC.Project.VCCustomBuildTool.Outputs
- VC.Project.VCCustomBuildTool.Command
- VC.Project.VCCustomBuildTool.CommandLine
- VC.Project.VCCustomBuildTool.AdditionalDependencies
- VC.Project.VCCustomBuildTool.Message
- VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets
- VC.Project.VCCustomBuildTool.Description
- VC.Project.VCCustomBuildTool.AdditionalInputs
dev_langs:
- C++
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b8fc10d2a94ab4b26a47991d3dc8923afb28ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="specify-custom-build-tools"></a>カスタム ビルド ツールを指定します。

A*カスタム ビルド ツール*ビルド システムを特定の入力ファイルをビルドする必要がある情報を提供します。 カスタム ビルド ツールは、実行するコマンドを入力ファイルの一覧のコマンドによって生成される出力ファイルの一覧と、ツールのオプションの説明を指定します。

カスタム ビルド ツールとカスタム ビルド ステップに関する概要については、次を参照してください。[カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)です。

### <a name="to-specify-a-custom-build-tool"></a>カスタム ビルド ツールを指定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)です。

1. 選択**構成プロパティ**を有効にする、**構成**ボックス。 **構成**ボックスで、カスタム ビルド ツールを指定する構成を選択します。

1. **ソリューション エクスプ ローラー**、カスタム ビルド ツールの入力ファイルを選択します。

   場合、**カスタム ビルド ツール**フォルダーが表示されない、選択したファイルのファイル拡張子は、既定のツールに関連付けられています。 たとえば、.c および .cpp ファイルの既定のツールは、コンパイラです。 既定のツールの設定を上書きする、**構成プロパティ**ノードで、**全般**フォルダーで、**項目の種類**プロパティを選択**カスタム ビルドツール**です。 選択**適用**と**カスタム ビルド ツール**ノードが表示されます。

1. **カスタム ビルド ツール**ノードで、**全般**フォルダー、ビルド ツールのユーザー設定に関連付けられたプロパティを指定します。

   - **追加の依存関係**、指定のファイル、カスタム ビルド ツールが定義されている以外の追加 (カスタム ビルド ツールに関連付けられているファイルは暗黙的と見なされます、ツールへの入力)。 追加の入力ファイルは、カスタム ビルド ツールの要件ではありません。 1 つ以上の入力を追加した場合は、セミコロンで区切ります。

      場合、**追加の依存関係**ファイルの日付は入力のファイルよりも後、カスタム ビルド ツールを実行します。 すべての場合の**追加の依存関係**ファイルは、入力ファイルより古い、入力ファイルはより古い、**出力**プロパティ ファイルにして、カスタム ビルド ツールは実行されません。

      たとえば、入力として MyInput.x を受け取りし、MyInput.cpp、および MyInput.x には MyHeader.h、ヘッダー ファイルが含まれている生成するカスタム ビルド ツールがあるとします。 MyInput.x または MyHeader.h に対して最新でないときに、ビルド システムが MyInput.cpp をビルドおよび MyInput.x への入力依存関係として MyHeader.h を指定できます。

      入力依存関係に必要な順序で、カスタム ビルド ツールを実行することも確認できます。 前の例では、MyHeader.h が実際にカスタム ビルド ツールの出力であるとします。 MyHeader.h MyInput.x の依存関係があるため、ビルド システムはまず構築されている MyInput.x でカスタム ビルド ツールを実行する前に Myheader.h を使用します。

   - **コマンドライン**、コマンド プロンプトで指定するかのようにコマンドを指定します。 有効なコマンドまたはバッチ ファイルを指定し、いずれかの必須入力または出力ファイル。 指定して、**呼び出す**バッチ ファイルの名前の前にすべての後続のコマンドが実行されることを保証するために、コマンドをバッチ処理します。

      複数の入力と出力ファイルは、MSBuild マクロでのシンボルで指定できます。 ファイルの場所または一連のファイルの名前を指定する方法については、次を参照してください。[のビルドのコマンドとプロパティの一般的なマクロ](../ide/common-macros-for-build-commands-and-properties.md)です。

      '%' 文字は、各環境変数を置き換える、指定した場合、MSBuild によって予約されているため**%** 文字をエスケープ、 **%25** 16 進数のエスケープ シーケンスです。 たとえば、置き換える **%windir%** で **%25windir 25**です。 各 MSBuild が置き換えられます **%25**とシーケンス、 **%** 文字の環境変数にアクセスする前にします。

   - **説明**、このカスタム ビルド ツールに関するわかりやすいメッセージを入力します。 メッセージが出力、**出力**ウィンドウ、ビルド システムがこのツールを処理するときにします。

   - **出力**、出力ファイルの名前を指定します。 これは、必要なエントリです。このプロパティの値でないと、カスタム ビルド ツールは実行されません。 カスタム ビルド ツールに 1 つ以上の出力がある場合は、ファイル名をセミコロンで区切ります。

      出力ファイルの名前は同じはずで指定されている、**コマンドライン**プロパティです。 プロジェクト ビルド システムは、ファイルを検索し、その日付を確認します。 出力ファイルは、入力ファイルより新しい場合、または出力ファイルが見つからない場合は、カスタム ビルド ツールを実行します。 すべての場合の**追加の依存関係**ファイルよりも古い、入力ファイルであり、入力ファイルに示されたファイルより古い、**出力**プロパティ、カスタム ビルド ツールは実行されません。

ビルド システムでカスタム ビルド ツールによって生成された出力ファイルを操作する場合は、手動でプロジェクトに追加する必要があります。 カスタム ビルド ツールは、ビルド時にファイルを更新します。

## <a name="example"></a>例

プロジェクトで parser.l をという名前のファイルを追加することを想定しています。 構文のアナライザーがある**lexer.exe**、実行可能ファイル パスにします。 同じ基本名 (parser.c) を持つ .c ファイルを生成するために parser.l の処理に使用するには。

最初に、プロジェクトに parser.l と parser.c を追加します。 ファイルがまだ存在しない場合は、ファイルへの参照を追加します。 Parser.l のカスタム ビルド ツールを作成しでは、次を入力、**コマンド**プロパティ。

> **字句解析器 %(FullPath) です。\%(ファイル名) .c**

このコマンドは、parser.l で構文、アナライザーを実行し、プロジェクト ディレクトリに parser.c を出力します。

**出力**プロパティ、次を入力します。

> **.\%(ファイル名) .c**

プロジェクトをビルドするときに、ビルド システムは parser.l parser.c のタイムスタンプを比較します。 Parser.l は最新のもので、またはビルド システムがの値を実行して parser.c が存在しない場合、**コマンドライン**parser.c 最新の状態を表示するプロパティです。 Parser.c は、プロジェクトに追加されてから、ビルド システムは、parser.c をコンパイルします。

## <a name="see-also"></a>関連項目

[ビルドのコマンドとプロパティの共通マクロ](../ide/common-macros-for-build-commands-and-properties.md)  
[ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)  
