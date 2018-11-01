---
title: '方法: カスタム ツールをプロジェクト プロパティに統合する'
ms.date: 04/27/2016
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: 7041e6583ba1e2c7f035edcc72617ccdb8d5aa02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633013"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>方法: カスタム ツールをプロジェクト プロパティに統合する

カスタム ツール オプションを追加するには、Visual studio**プロパティ ページ**ウィンドウを基になる XML スキーマ ファイルを作成します。

**構成プロパティ**のセクション、**プロパティ ページ**ウィンドウと呼ばれる設定グループが表示されます。*ルール*します。 すべてのルールには、ツールまたは機能のグループの設定が含まれています。 たとえば、**リンカー**ルールには、リンカー ツールの設定が含まれています。 ルールの設定に分割できる*カテゴリ*します。

このドキュメントでは、Visual Studio の起動時に、プロパティが読み込まれるように、カスタム ツールのプロパティを含むセット ディレクトリにファイルを作成する方法について説明します。 ファイルを変更する方法については、次を参照してください。[プラットフォーム機能拡張の第 2 部](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/)Visual Studio プロジェクトのチームのブログ。

### <a name="to-add-or-change-project-properties"></a>プロジェクトのプロパティを追加または変更

1. XML エディターでは、XML ファイルを作成します。

1. Visual Studio 2017 でファイルを保存`VCTargets\1033`フォルダー。 インストールされている Visual Studio 2017 の各エディションと言語ごとに異なるパスになります。 たとえば、英語版の Visual Studio Enterprise edition のフォルダー パスは`%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`します。 言語と Visual Studio のエディションの経路を調整します。 すべてのルールで、**プロパティ ページ**ウィンドウはこのフォルダー内の XML ファイルで表されます。 フォルダー内のファイルの名前は一意にすることを確認します。

1. 内容をコピー`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`変更を保存しないで閉じます、および、新しい XML ファイルにコンテンツを貼り付けます。 任意の XML スキーマ ファイルを使用する - これは、テンプレートを使用して開始するために使用できる機能を 1 つ。

1. 新しい XML ファイルでは、ニーズに合わせてコンテンツを変更します。 変更することを確認、**ルール名**と**Rule.DisplayName**ファイルの上部にあります。

1. 変更を保存し、ファイルを閉じます。

1. XML ファイル`%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>`は、Visual Studio の起動時に読み込まれます。 そのため、新しいファイルをテストするには、Visual Studio を再起動します。

1. **ソリューション エクスプ ローラー**プロジェクトを右クリックし、クリックして**プロパティ**します。 **プロパティ ページ**ウィンドウで、左側のウィンドウで、ルールの名前を持つ新しいノードがあることを確認します。

## <a name="see-also"></a>関連項目

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
