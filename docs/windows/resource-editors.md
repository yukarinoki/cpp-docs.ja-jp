---
title: リソース エディター (C++)
ms.date: 02/14/2019
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
ms.openlocfilehash: a0b5e3905daf72307702dbe4f05c2871cf768ac0
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328806"
---
# <a name="resource-editors-c"></a>リソース エディター (C++)

リソース エディターは、作成または Visual Studio プロジェクトに含まれているリソースを変更するための特殊な環境です。 Visual Studio のリソース エディターでは、アプリケーションのリソースをすばやく簡単に作成して変更できるようにする技術とインターフェイスを共有します。 リソース エディターを使用すると、表示し、適切なエディターとプレビューのリソースでリソースを編集できます。

リソースを作成したり開いたりすると、適切なエディターが自動的に開きます。

> [!NOTE]
> マネージ プロジェクトでは、リソース スクリプト ファイルは使用しないのでからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 使用することができます、[イメージ エディター](../windows/image-editor-for-icons.md)と[バイナリ エディター](binary-editor.md)マネージ プロジェクトのリソース ファイルを使用します。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

|使用|編集|
|----------------|----------------|
|[アクセラレータ エディター](../windows/accelerator-editor.md)|アクセラレータ テーブル (Visual C++ プロジェクトでの)|
|[Binary Editor](binary-editor.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのバイナリ データの情報およびカスタム リソース。|
|[ダイアログ エディター](../windows/dialog-editor.md)|ダイアログ ボックス (Visual C++ プロジェクトでの)|
|[Image Editor](../windows/image-editor-for-icons.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのビットマップ、アイコン、カーソル、およびその他のイメージ ファイル。|
|[メニュー エディター](../windows/menu-editor.md)|Visual C++ プロジェクトのメニュー リソース。|
|[Ribbon エディター](../mfc/ribbon-designer-mfc.md)|MFC プロジェクトのリボン リソース。|
|[ストリング エディター](../windows/string-editor.md)|文字列テーブル (Visual C++ プロジェクトでの)|
|[ツール バー エディター](../windows/toolbar-editor.md)|Visual C++ プロジェクトのツール バー リソース。 **ツール バー エディター**の一部である、**イメージ エディター**します。|
|[バージョン エディター](../windows/version-information-editor.md)|Visual C++ プロジェクトのバージョン情報です。|

> [!NOTE]
> 場合は、プロジェクトに .rc ファイル含まれていないを参照してください[方法。リソースを作成する](../windows/how-to-create-a-resource-script-file.md)します。

## <a name="view-and-edit-resources"></a>ビューと編集リソース

各リソースの種類には、そのリソースの種類に固有のリソース エディターが用意されています。 再配置してサイズ変更、コントロールと機能を追加するか、またはそれ以外の場合、関連付けられているエディターを使用してリソースの側面を変更できます。 内のリソースを編集することもできます。[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)と[バイナリ形式](../windows/opening-a-resource-for-binary-editing.md)します。

リソースの種類によっては個々 のファイルをインポートしてさまざまな方法で使用されることができます。ビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソースがあるファイル名と[リソース識別子](../windows/symbols-resource-identifiers.md)します。 他のユーザー、ダイアログ、メニューのおよび Win32 プロジェクトの文字列テーブルなど存在リソース スクリプト (.rc) ファイルまたはリソース テンプレート (.rct) ファイルの一部としてのみです。

リソースがすることもできますを参照してください、プロジェクトを開かずに、プロジェクトの外部で編集、[方法。リソースを作成する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

> [!NOTE]
> 使用してリソースのプロパティを変更できる、**プロパティ**ウィンドウ。

- リソースのプロパティを編集する[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)、編集するリソースを右クリックして**プロパティ**します。  次に、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)リソースのプロパティを変更します。

- リソースのプロパティに加えられた変更を元に戻すには、リソース フォーカスを確認します**リソース ビュー**選択**を元に戻す**から、**編集**メニュー。

### <a name="win32-resources"></a>Win32 リソース

Win32 リソースにアクセスすることができます、[リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)ウィンドウ。

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>リソース エディターで、Win32 リソースを表示するには

1. メニューに移動して**ビュー** > **リソース ビュー**します。

1. 場合、**リソース ビュー**最上位のウィンドウでは、select 以外のウィンドウ、**リソース ビュー**上部にタブ。

1. **リソース ビュー**、表示するリソースを含むプロジェクトのフォルダーを展開します。 たとえば、ダイアログ リソースを表示する場合は、展開、**ダイアログ**フォルダー。

1. たとえば、リソースをダブルクリックして**IDD_ABOUTBOX**します。

   リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースの場合は、リソースで開きます、**ダイアログ エディター**します。

#### <a name="to-delete-an-existing-win32-resource"></a>既存の Win32 リソースを削除するには

1. **リソース ビュー**リソースの種類のノードを展開します。

1. 削除するリソースを右クリックして**削除**します。

> [!TIP]
> .Rc ファイルをプロジェクトの外部のドキュメント ウィンドウで開いているときに、このメソッドを使用することもできます。

### <a name="managed-project-resources"></a>マネージ プロジェクトのリソース

マネージ プロジェクトでは、リソース スクリプト ファイルを使用しないためにからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 使用して、[イメージ エディター](../windows/image-editor-for-icons.md)と[バイナリ エディター](binary-editor.md)マネージ プロジェクトのリソース ファイルを使用します。 リンク リソースである必要がありますのマネージ リソースを編集して、Visual Studio のリソース エディターが埋め込まれたリソースの編集をサポートしていません。

- リソース エディターでマネージ リソースを表示する**ソリューション エクスプ ローラー**など、リソースをダブルクリックして*Bitmap1.bmp*、および、リソースが適切なエディターで開きます。

- 既存のマネージ リソースを削除する**ソリューション エクスプ ローラー**、削除するリソースを右クリックして**削除**します。

## <a name="preview-resources"></a>プレビューのリソース

グラフィカル リソースを開かずに表示できるように、リソースをプレビューします。 プレビューも便利です実行可能ファイルに対して、それらをコンパイルした後にリソース識別子を数値に変更されます。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューでそれらをすばやく識別できます。

次のリソースの種類は、視覚的なレイアウトのプレビューを提供します。ビットマップ、ダイアログ、アイコン、メニューのカーソル、ツールバー

次のリソースには、ビジュアルのプレビューを提供しません。アクセラレータ、マニフェスト、文字列テーブルでは、バージョン情報

> [!NOTE]
> リソースをプレビューするには、Win32 が必要です。

### <a name="to-preview-resources"></a>リソースをプレビューするには

1. [リソース ビュー](how-to-create-a-resource-script-file.md#create-resources)または、リソースを選択して、ドキュメント ウィンドウ**IDD_ABOUTBOX**します。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を選択、**プロパティ ページ**ボタンをクリックします。

   > [!TIP]
   > ショートカットを使用して、メニューに移動して、**ビュー** > **プロパティ ページ**します。

   **プロパティ**リソースのページが開き、リソースのプレビューを表示します。 使用することができます、**を**と**ダウン**ツリーを移動する方向キーを制御**リソース ビュー**またはドキュメント ウィンドウ。 **プロパティ**ページは開いたままし、フォーカスがあり、プレビューできる任意のリソースを表示します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>