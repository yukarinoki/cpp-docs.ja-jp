---
ms.openlocfilehash: e2b88bb1c60c97c9f63caacfb98ba87e0443e799
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509441"
---
# <a name="contributing"></a>コントリビューション

Visual C++ ドキュメントへの貢献に関心をお寄せいただきありがとうございます。

このトピックでは、[Visual C++ ドキュメント サイト](https://docs.microsoft.com/cpp)のコンテンツを追加または更新するための基本プロセスについて説明します。

このトピックの内容:

* [投稿のプロセス](#process-for-contributing)
* [注意事項](#dos-and-donts)
* [ドキュメントの構築](#building-the-docs)
* [サンプルへの投稿](#contributing-to-samples)
* [共同作成者ライセンス条項](#contributor-license-agreement)

## <a name="process-for-contributing"></a>投稿のプロセス

**手順 1:** 作成する記事と既存のコンテンツとの関連を説明する問題を開きます。
**docs** フォルダー内の内容は、コンテンツ領域 (デバッガーなど) 別に編成されたセクションに編成されています。 新しいコンテンツ用の適切なフォルダーを特定します。 提案に対するフィードバックを得ます。

小さな変更の場合はこの最初の手順をスキップできます。

**手順 2:**`MicrosoftDocs/cpp-docs` リポジトリをフォークします。

**手順 3:** 記事の `branch` を作成します。

**手順 4:** 記事を作成します。

新しいトピックの場合は、この[テンプレート ファイル](./styleguide/template.md)を開始点として使用できます。 このファイルには、作成のガイドラインが含まれ、作成者情報など、記事ごとに必要なメタデータについても説明されています。

手順 1 で、ご自分の記事について特定した TOC の場所に対応するフォルダーに移動します。
そのフォルダーには、そのセクション内のすべての記事のマークダウン ファイルが格納されています。 必要に応じて、ご自分のコンテンツ用のファイルを格納する新しいフォルダーを作成します。

イメージとその他の静的リソースについては、`media` という名前のサブフォルダーに追加します。 コンテンツ用の新しいフォルダーを作成する場合は、新しいフォルダーに media フォルダーを追加します。

適切なマークダウン構文に従ってください。 詳細については、[スタイル ガイド](./styleguide/template.md)を参照してください。

### <a name="example-structure"></a>構造の例

```
docs
    /standard-library
        wstring-convert-class.md
        /media
            wstring-conversion.png
```

**手順 5:** ご自分のブランチから `MicrosoftDocs/cpp-docs/master` に Pull Request (PR) を送信します。

PR が既存の問題に対処している場合は、コミット メッセージまたは PR の説明に `Fixes #Issue_Number` キーワードを追加すると、PR がマージされたときに問題が自動的に閉じられます。 詳細については、[コミット メッセージによって問題を閉じる](https://help.github.com/articles/closing-issues-via-commit-messages/)方法についての記事を参照してください。

Visual Studio チームが PR を確認し、変更が適切であるか、または変更を承認するために必要な他の更新や変更があるかどうかをお知らせします。

**手順 6:** チームによって説明されたとおりに、ご自分のブランチに必要な更新を加えます。

フィードバックが適用され、変更が適切であるように見える場合は、保守管理者によって、PR がマスター ブランチにマージされます。

特定の周期で、マスター ブランチのすべてのコミットがライブ ブランチにプッシュされるので、[docs.microsoft.com](https://docs.microsoft.com/cpp/) でライブでご自分の投稿を確認できます。

## <a name="dos-and-donts"></a>注意事項

.NET ドキュメントに投稿する際に注意する必要があるガイド ルールの簡単な一覧を次に示します。

- 突然に、巨大な pull requests を送信**しないでください**。 代わりに、問題を提出し、ディスカッションを開始して、大量の時間を費やす前に方向について同意が得られるようにしてください。
- [スタイル ガイド](./styleguide/template.md)と[スタイルとトーン](./styleguide/voice-tone.md)のガイドラインを**お読みください**。
- [テンプレート](./styleguide/template.md) ファイルを作業の開始点として**使用してください**。
- 記事に取り掛かる前に、フォークに個別のブランチを**作成してください**。
- [GitHub フロー ワークフロー](https://guides.github.com/introduction/flow/)に**従ってください**。
- 投稿について頻繁にブログやツイート**を書いてください**。

> [!NOTE]
> 一部のトピックが現在、この記事や[スタイル ガイド](./styleguide/template.md)に指定されたすべてのガイドラインに従っていないことに気付く場合があります。 Microsoft では、サイト全体で一貫性の達成に向けて取り組んでいます。 その特定の目標に向けて現在追跡中の[未解決の問題](https://github.com/MicrosoftDocs/cpp-docs/issues?q=is%3Aissue+is%3Aopen+label%3Aguidelines-adherence)の一覧をご確認ください。

## <a name="building-the-docs"></a>ドキュメントの構築

ドキュメントは、[GitHub Flavored Markdown](https://help.github.com/categories/writing-on-github/) を使用して書かれており、[DocFX](https://dotnet.github.io/docfx/) とその他の内部公開/構築ツールを使用して構築されています。 ドキュメントは、[docs.microsoft.com](https://docs.microsoft.com/) でホストされています。

ドキュメントをローカルで構築する場合は、[DocFX](https://dotnet.github.io/docfx/) をインストールする必要があり、この最新バージョンが最適です。

DocFX を使用する方法はいくつかありますが、そのほとんどは、[DocFX のファースト ステップ ガイド](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)に記載されています。 次の手順では、[コマンド ライン ベース](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html#2-use-docfx-as-a-command-line-tool)のバージョンのツールを使用しています。 上記のリンクに記載されている他の方法が使いやすい場合は、それらを使用してもかまいません。

**注:** 現在、DocFX には Windows または Mono (Linux または macOS 用) 上の .NET Framework が必要です。 将来 .NET Core に移植されることが望まれます。

組み込みの Web サーバーを使用して、ローカルで結果のサイトをビルドしてプレビューできます。 コンピューター上の `cpp-docs\docs` フォルダーに移動し、次のコマンドを入力します。

> docfx -t default --serve

これにより、[localhost:8080](http://localhost:8080) でローカル プレビューが起動されます。 変更を表示するには、`http://localhost:8080/[path]` (`http://localhost:8080/cpp/visual-cpp-in-visual-studio.html` など) に移動します。

**注:** ローカル プレビューには現在のところテーマが含まれないため、ドキュメント サイト内とルック アンド フィールが同じになりません。 この操作については修正中です。 プレビューでは表示されない、埋め込みのビデオ、ノート、含まれているドキュメントに対してはカスタム拡張機能も使用します。

## <a name="contributing-to-samples"></a>サンプルへの投稿

現在のところ、必要なサンプル コードはインライン コード ブロックとして記事に含めます。 リポジトリには `codesnippets` フォルダーがありますが、これは公開投稿向けに準備されていません。

## <a name="contributor-license-agreement"></a>共同作成者ライセンス条項

PR がマージされる前に、[貢献者使用許諾契約書 (CLA)](LICENSE) に署名する必要があります。 これは、docs.microsoft.com 内のプロジェクトに対して 1 回だけ必要です。 [貢献者使用許諾契約書 (CLA)](https://en.wikipedia.org/wiki/Contributor_License_Agreement) について詳しくは、Wikipedia を参照してください。

前もって契約に署名する必要はありません。 PR は通常どおり、複製、フォーク、送信できます。 PR が作成されると、CLA ボットで分類されます。 変更が軽微である (入力ミスの修正など) 場合は、PR に CLA-not-required のラベルが付けられます。 それ以外の場合は、CLA-required と分類されます。 CLA への署名後は、現在以降のすべての pull requests に、CLA-singed のラベルが付けられます。
