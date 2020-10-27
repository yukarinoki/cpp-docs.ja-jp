---
title: '方法: カスタム ツールをプロジェクトのプロパティに統合する'
description: Visual Studio C++ プロジェクトでカスタム ツールをプロジェクト プロパティに統合する方法。
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), howto: integrate custom tools'
ms.openlocfilehash: 4b88bf94a92efaf5046fd83e5c6358f3fdf80895
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099668"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>方法: カスタム ツールをプロジェクトのプロパティに統合する

XML ファイルを作成することにより、Visual Studio の **[プロパティ ページ]** ウィンドウにカスタム ツール オプションを追加できます。

**[プロパティ ページ]** ウィンドウの **[構成プロパティ]** セクションには、" *ルール* " と呼ばれる設定グループが表示されます。 すべてのルールには、ツールまたは機能のグループの設定が含まれています。 たとえば、 **[リンカー]** ルールには、リンカー ツールの設定が含まれています。 ルールの設定は、" *カテゴリ* " に分かれている場合があります。

カスタム ツールのプロパティを含むルール ファイルを作成して、Visual Studio の起動時にプロパティが読み込まれるようにすることができます。 ファイルを変更する方法については、Visual Studio プロジェクト チーム ブログの「[ラットフォームの拡張性 - パート 2](/archive/blogs/vsproject/platform-extensibility-part-2)」をご覧ください。

::: moniker range="vs-2015"

ルール ファイルを配置するフォルダーは、使用している Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* です。 Visual Studio 2015 の場合、`<version>` 値は *`v140`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2015 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* になります。

::: moniker-end

::: moniker range="vs-2017"

ルール ファイルを配置するフォルダーは、使用している Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2017 の開発者コマンド プロンプトの場合、ルール フォルダーは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* です。`<version>` 値は Visual Studio 2015 の場合は *`v140`* です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2017 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* になります。

::: moniker-end

::: moniker range=">=vs-2019"

ルール ファイルを配置するフォルダーは、使用している Visual Studio のロケールとバージョンによって異なります。 Visual Studio 2019 以降の開発者コマンド プロンプトのルール フォルダーは *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* です。Visual Studio 2019 の場合、`<version>` 値は *`v160`* です。 `<locale>` は LCID です。たとえば、英語の場合は `1033` です。 Visual Studio 2017 の場合、ルール フォルダーは *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* です。 Visual Studio 2015 以前の開発者コマンド プロンプトの場合、ルール フォルダーは *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* です。 インストールされている Visual Studio のエディションおよび言語ごとに異なるパスを使用します。 たとえば、Visual Studio 2019 Community エディションの英語版の既定のルール フォルダー パスは *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* になります。

::: moniker-end

### <a name="to-add-or-change-project-properties"></a>プロジェクトのプロパティを追加または変更するには

1. XML エディターで XML ファイルを作成します。

1. 既定のルール フォルダーにファイルを保存します。 言語と Visual Studio のエディションに合わせてパスを調整します。 **[プロパティ ページ]** ウィンドウのすべてのルールは、このフォルダー内の XML ファイルによって表されます。 ファイルの名前がフォルダー内で一意になっていることを確認します。

1. *`rc.xml`* などの既存のルール ファイルの内容をコピーし、変更を保存せずに閉じてから、新しい XML ファイルにその内容を貼り付けます。 任意の XML スキーマ ファイルをコピーして、テンプレートとして使用することができます。 ご使用のツールに似たものを選択してください。

1. 新しい XML ファイルで、必要に応じて内容を変更します。 ファイルの先頭にある **Rule Name** と **Rule.DisplayName** を必ず変更します。

1. 変更を保存し、ファイルを閉じます。

1. ルール フォルダー内の XML ファイルは、Visual Studio の起動時に読み込まれます。 新しいファイルをテストするには、Visual Studio を再起動します。

1. **ソリューション エクスプローラー** でプロジェクトを右クリックし、 **[プロパティ]** を選択します。 **[プロパティ ページ]** ウィンドウで、ご自分のルールの名前を持つ新しいノードがあることを確認します。

## <a name="see-also"></a>関連項目

[コマンド ラインでの MSBuild - C++](msbuild-visual-cpp.md)
