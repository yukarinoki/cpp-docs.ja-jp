---
title: 'vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー'
description: vcpkg は、Windows、Linux、および macOS でのオープン ソースの C++ ライブラリの取得およびインストール作業を大幅に簡素化するコマンド ライン パッケージ マネージャーです。
ms.custom: contperf-fy21q2
ms.date: 12/11/2020
ms.topic: overview
ms.technology: cpp-ide
ms.openlocfilehash: 23ad9b34a04791181b83bcae3d413d6dfe0eed00
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099600"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows、Linux、および macOS 用の C++ パッケージ マネージャー

vcpkg は、C および C++ のライブラリのクロスプラットフォームのコマンドライン パッケージ マネージャーです。 これにより、Windows、Linux、macOS のサードパーティー ライブラリが簡単に取得およびインストールできます。 プロジェクトでサードパーティ ライブラリを使用する場合は、vcpkg を使用して、それらをインストールすることをお勧めします。 vcpkg では、オープン ソース ライブラリと専用ライブラリの両方がサポートされています。 vcpkg Windows カタログ内のすべてのライブラリは、Visual Studio 2015、Visual Studio 2017、Visual Studio 2019 との互換性がテストされています。 Windows と Linux/macOS のカタログ間で、vcpkg は現在、何千ものライブラリをサポートしています。 両カタログには、C++ のコミュニティによりライブラリが継続的に追加されています。

## <a name="how-to-get-and-use-vcpkg"></a>vcpkg を取得して使用する方法

GitHub リポジトリ [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) から vcpkg をローカルに複製しインストールします。 それから vcpkg-bootstrapper スクリプトを実行して設定します。 インストールの詳細な手順については、[vcpkg のインストール](install-vcpkg.md)に関する説明を参照してください。 vcpkg をお使いの Visual Studio または Visual Studio Code の開発環境に統合するには、[vcpkg の統合](integrate-vcpkg.md)に関する説明を参照してください。 その後、vcpkg を使用してライブラリをインストールまたは更新する場合は、「[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)」を参照してください。 vcpkg のコマンドの詳細については、[vcpkg のコマンド ライン リファレンス](vcpkg-command-line-reference.md)に関する説明を参照してください。

## <a name="how-vcpkg-works"></a>vcpkg のしくみ

vcpkg は、オープンソースのプロジェクトで、GitHub から入手できます。 vcpkg リポジトリの "*複製*" またはローカル コピーには、vcpkg の実行可能ファイルと "*カタログ*"、ライブラリとそのオプションが記述されたパッケージの一覧が含まれています。 各パッケージには、特定のターゲット環境における 1 つ以上の "*ポート*"、ソースからライブラリを取得してビルドする方法、またはバイナリのバージョンをダウンロードする方法に関する情報が含まれています。 vcpkg を使用してライブラリをインストールすると、パッケージとポートの情報を使用して、そのライブラリのローカル コピーが vcpkg ディレクトリのサブディレクトリにダウンロードされ生成されて、使用できるようになります。

ライブラリをソース形式で使用できる場合、vcpkg はバイナリではなくソースをダウンロードします。 それらのソースは、見つけることのできる C または C++ コンパイラおよびツールの最新バージョンを使ってコンパイルされます。 C++ ABI との整合性のために、お使いのアプリケーション コードと使用するすべてのライブラリの両方が、同じバージョンの同じコンパイラでコンパイルされていることが重要です。 vcpkg を使用すると、バイナリが一致しない可能性と、それによって問題が生じる可能性がなくなるか、大幅に減少します。 特定のバージョンのコンパイラを標準で使用しているチームでは、1 人のチーム メンバーが vcpkg を使用してソースをダウンロードし、一連のバイナリをコンパイルします。 チームのすべてのユーザーが同じライブラリをダウンロードしてビルドすることは、効率的ではありません。 1 人のチーム メンバーが **`vcpkg export`** コマンドを使用して、バイナリとヘッダー、または NuGet パッケージの共用の zip ファイルを作成します。 その後、他のチーム メンバーと共有すると簡単です。

## <a name="customize-vcpkg-instances-for-different-targets"></a>異なるターゲット用の vcpkg インスタンスのカスタマイズ

自分のコンピューターで vcpkg のコピーまたは "*インスタンス*" を複数複製して、それぞれを特定の用途にカスタマイズできます。 各インスタンスに、別のライブラリをインストールしたり、パブリック カタログのものとは異なるバージョンのライブラリをインストールしたりすることができます。 各インスタンスは、自分の好きなコンパイラ オプションを使用して、ライブラリのカスタム コレクションを生成するように設定できます。 各インスタンスは自己完結型の環境であり、その階層のみで動作する vcpkg.exe の独自のコピーがあります。 vcpkg はどの環境変数にも追加されず、Windows レジストリや Visual Studio に依存していません。

また、ポートのコレクションにプライベート ライブラリを持つ vcpkg クローンを作成することもできます。 自分で事前作成したバイナリとヘッダーをダウンロードするポートを追加できます。 次に、それらのファイルを適切な場所に単にコピーする *portfile.cmake* ファイルを記述します。

## <a name="the-vcpkg-folder-hierarchy"></a>vcpkg のフォルダー階層

vcpkg のすべての機能とデータは、インスタンスごとに 1 つのディレクトリ階層で自己完結しています。 レジストリの設定や環境変数はありません。 1 台のコンピューターで、相互に干渉しない vcpkg のインスタンスはいくつでも使用できます。

vcpkg インスタンスの内容は次のとおりです。

- *`buildtrees`* - 各ライブラリの作成元となるソースのサブフォルダーが含まれています。
- *`docs`* - ドキュメントと例。
- *`downloads`* - ダウンロードしたツールまたはソースのキャッシュ コピー。 vcpkg は、インストール コマンドの実行時に最初にここを検索します。
- *`installed`* - インストールされている各ライブラリのヘッダーとバイナリが含まれています。 Visual Studio と統合する場合、基本的にこのフォルダーがその検索パスに追加されます。
- *`packages`* - インストール間のステージング用の内部フォルダー。
- *`ports`* - カタログ内の各ライブラリ、そのバージョン、およびダウンロード場所が記述されたファイル。 必要に応じて、独自のポートを追加できます。
- *`scripts`* - vcpkg で使用されるスクリプト (CMake、PowerShell)。
- *`toolsrc`* - vcpkg および関連するコンポーネントの C++ ソース コード。
- *`triplets`* - サポートされているターゲット プラットフォーム (x86-windows や x64-uwp など) の設定が含まれます。

## <a name="telemetry"></a>テレメトリ

vcpkg は、ユーザーのエクスペリエンスを向上するために使用状況データを収集します。 このデータは Microsoft によって匿名で収集されます。 テレメトリをオプトアウトするには、 **`-disableMetrics`** オプションを使用し、 **`bootstrap-vcpkg.bat`** または **`bootstrap-vcpkg.sh`** スクリプトを再実行します。 または、コマンド ラインで vcpkg に **`--disable-metrics`** オプションを渡します。 メトリックを、`VCPKG_DISABLE_METRICS` 環境変数を設定して無効にすることもできます。

## <a name="send-feedback-about-vcpkg"></a>vcpkg のフィードバックを送信する

バグ報告や機能の提案など、vcpkg に関するフィードバックを Microsoft に送信するには、 **`vcpkg contact --survey`** コマンドを使用します。 詳細については、[vcpkg のコマンドライン リファレンス](vcpkg-command-line-reference.md)に関する説明を参照してください。

## <a name="see-also"></a>関連項目

[GitHub 上の vcpkg](https://github.com/Microsoft/vcpkg)\
[vcpkg をインストールする](install-vcpkg.md)\
[vcpkg を統合する](integrate-vcpkg.md)\
[vcpkg を使用してライブラリを管理する](manage-libraries-with-vcpkg.md)\
[vcpkg コマンドライン リファレンス](vcpkg-command-line-reference.md)\
[クイック スタート](https://github.com/microsoft/vcpkg/blob/master/docs/README.md)\
[よく寄せられる質問](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
