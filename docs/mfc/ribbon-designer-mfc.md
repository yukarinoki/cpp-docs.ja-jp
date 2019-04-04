---
title: リボン デザイナー (MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: 5740b2f93f451a74407483c98ce5bf547b79bf35
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769486"
---
# <a name="ribbon-designer-mfc"></a>リボン デザイナー (MFC)

リボン デザイナーを使用すると、MFC アプリケーションでリボンを作成してカスタマイズできます。 リボンは、複数のコマンドを 1 つの論理グループにまとめたユーザー インターフェイス (UI) 要素です。 これらのグループは、ウィンドウの上部に水平に並んで表示されるタブに別々に表示されます。 リボンは、メニュー バーとツール バーの代わりに表示されます。 リボンは、アプリケーションの使用性を大幅に向上させます。 詳細については、[リボン](/windows/desktop/uxguide/cmd-ribbons)を参照してください。 リボンを次の図に示します。

![MFC リボン リソース コントロール](../mfc/media/ribbon_no_callouts.png "MFC リボン リソース コントロール")

リボンを Visual Studio の以前のバージョンなどの MFC リボン クラスを使用するコードを記述することで作成する必要がある[CMFCRibbonBar クラス](../mfc/reference/cmfcribbonbar-class.md)します。 Visual Studio 2010 以降では、リボン デザイナーは、リボンを構築するための別の方法を提供します。 最初に、リボンをリソースとして作成およびカスタマイズします。 次に、リボン リソースを MFC アプリケーションのコードから読み込みます。 リボン リソースと MFC リボン クラスを同時に使用することもできます。 たとえば、リボン リソースを作成でき、プログラムで要素を追加して実行時にコードを使用してできます。

## <a name="understanding-the-ribbon-designer"></a>リボン デザイナーについて

リボン デザイナーは、リボンをリソースとして作成および保存します。 リボン リソースを作成すると、リボン デザイナーによって次の 3 つの操作が行われます。

- プロジェクト リソース定義スクリプト (*.rc) にエントリを追加する。 次の例では、IDR_RIBBON はリボン リソースを識別する一意の名前、RT_RIBBON_XML は、リソースの種類および ribbon.mfcribbon ms はリソース ファイルの名前です。

```
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- コマンド ID の定義を resource.h に追加する。

```
#define IDR_RIBBON            307
```

- リボンのボタン、コントロール、および属性を定義する XML コードを含むリボン リソース ファイル (*.mfcribbon-ms) を作成する。 リボン デザイナーで行ったリボンの変更は、リソース ファイルに XML として保存されます。 次のコード例の内容の一部を示しています、 \*.mfcribbon-ms ファイル。

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

MFC アプリケーションでリボン リソースを使用するには、呼び出すことによって、リソースを読み込む[cmfcribbonbar::loadfromresource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource)します。

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>リボン デザイナーを使用したリボンの作成

リボン リソースを MFC プロジェクトに追加する方法は 2 つあります。

- MFC アプリケーションを作成し、リボンを作成するように MFC プロジェクト ウィザードを構成する。 詳細については、「[チュートリアル:MFC によるリボン アプリケーションの作成](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)です。

- 既存の MFC プロジェクトにリボン リソースを作成し、それを読み込む。 詳細については、「[チュートリアル:MFC Scribble アプリケーション (パート 1) の更新](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)します。

プロジェクトに手動でコード化されたリボンが既に存在する場合でも、MFC には既存のリボンをリボン リソースに変換するために使用できる機能が用意されています。 詳細については、「[方法 :既存の MFC リボンをリボン リソースに変換](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md)します。

> [!NOTE]
>  リボンはダイアログ ベースのアプリケーションには作成できません。 詳細については、[アプリケーションの種類、MFC アプリケーション ウィザード](../mfc/reference/application-type-mfc-application-wizard.md)を参照してください。

## <a name="customizing-ribbons"></a>リボンのカスタマイズ

リボン デザイナーでリボンを開くには、リソース ビューでリボン リソースをダブルクリックします。 デザイナーでは、リボン、アプリケーション ボタン、またはクイック アクセス ツール バーに対する要素の追加、削除、およびカスタマイズを実行できます。 さらに、イベント (ボタン クリック イベントやメニュー イベントなど) をアプリケーション内のメソッドにリンクできます。

リボン デザイナーのさまざまなコンポーネントを次の図に示します。

![MFC リボン デザイナー](../mfc/media/ribbon_designer.png "MFC リボン デザイナー")

- **ツールボックス:** デザイナー画面にドラッグできるコントロールが含まれています。

- **デザイナー画面:** リボン リソースの視覚的表現が含まれています。

- **プロパティ ウィンドウ:** デザイナー画面で選択されている項目の属性を一覧表示します。

- **リソース ビュー ウィンドウ:** プロジェクトでリボン リソースを含むリソースを表示します。

- **Ribbon エディター ツールバー:** リボンのプレビューやビジュアル テーマを変更するコマンドが含まれています。

次のトピックでは、リボン デザイナーの機能の使用方法について説明します。

- [方法: アプリケーション ボタンをカスタマイズします。](../mfc/how-to-customize-the-application-button.md)

- [方法: クイック アクセス ツールバーをカスタマイズします。](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [方法: リボン コントロールとイベント ハンドラーを追加します。](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [方法: MFC アプリケーションからリボン リソースを読み込む](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>リボン要素の定義

![MFC リボン](../mfc/media/ribbon.png "MFC リボン")

- **アプリケーション ボタンをクリックします。** リボンの左上隅に表示されるボタン。 アプリケーション ボタンは [ファイル] メニューの代わりに表示され、リボンが最小化されている場合でも表示されます。 このボタンをクリックすると、コマンド リストを含むメニューが表示されます。

- **クイック アクセス ツールバー:** 使用されるコマンドをカスタマイズ可能な小規模のツールバーで、頻繁に表示されます。

- **カテゴリ**:リボン タブの内容を表す論理的なグループ。

- **カテゴリの既定のボタン:** リボンを最小化したときに、リボンに表示されるボタンをクリックします。 このボタンをクリックすると、カテゴリがメニューとして再表示されます。

- **パネル:** 関連するコントロールのグループを表示するリボン バーの領域。 すべてのリボン カテゴリには、1 つ以上のリボン パネルが含まれます。

- **リボン要素:** ボタンとコンボ ボックスなどのパネルで制御します。 リボン上をホストできるさまざまなコントロールを表示する、次を参照してください。 [RibbonGadgets サンプル。ガジェット アプリケーションのリボン](../overview/visual-cpp-samples.md)します。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)<br/>
[リソース ファイルの操作](../windows/working-with-resource-files.md)
