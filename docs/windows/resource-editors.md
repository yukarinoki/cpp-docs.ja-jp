---
title: リソース エディター (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 43eab011cefed116723bd983b685c1c8c230326f
ms.sourcegitcommit: bec1480a03e7b4070b469a6c131a69f516bbac70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56226320"
---
# <a name="resource-editors-c"></a>リソース エディター (C++)

A**リソース**エディターは、専用の環境の作成または Visual Studio プロジェクトに含まれているリソースを変更します。 Visual Studio のリソース エディターでは、アプリケーションのリソースをすばやく簡単に作成して変更できるようにする技術とインターフェイスを共有します。 リソース エディターを使用すると、表示し、適切なエディターとプレビューのリソースでリソースを編集できます。

リソースを作成したり開いたりすると、適切なエディターが自動的に開きます。

> [!NOTE]
> マネージ プロジェクトでは、リソース スクリプト ファイルは使用しないのでからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

|使用|編集|
|----------------|----------------|
|[アクセラレータ エディター](../windows/accelerator-editor.md)|アクセラレータ テーブル (Visual C++ プロジェクトでの)|
|[Binary Editor](binary-editor.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのバイナリ データの情報およびカスタム リソース。|
|[ダイアログ エディター](../windows/dialog-editor.md)|ダイアログ ボックス (Visual C++ プロジェクトでの)|
|[Image Editor](../windows/image-editor-for-icons.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのビットマップ、アイコン、カーソル、およびその他のイメージ ファイル。|
|[メニュー エディター](../windows/menu-editor.md)|Visual C++ プロジェクトのメニュー リソース。|
|[Ribbon エディター](../mfc/ribbon-designer-mfc.md)|MFC プロジェクトのリボン リソース。|
|[ストリング エディター](../windows/string-editor.md)|文字列テーブル (Visual C++ プロジェクトでの)|
|[ツール バー エディター](../windows/toolbar-editor.md)|Visual C++ プロジェクトのツール バー リソース。 ツール バー エディターは、イメージ エディターの一部です。|
|[バージョン エディター](../windows/version-information-editor.md)|Visual C++ プロジェクトのバージョン情報です。|

## <a name="view-and-edit-resources-in-a-resource-editor"></a>リソースはリソース エディターで表示して編集

各リソースの種類が、**リソース**そのリソースの種類に固有のエディター。 再配置してサイズ変更、コントロールと機能を追加するか、またはそれ以外の場合、関連付けられているエディターを使用してリソースの側面を変更できます。 内のリソースを編集することもできます。[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)と[バイナリ形式](../windows/opening-a-resource-for-binary-editing.md)します。

リソースの種類によっては個々 のファイルをインポートしてさまざまな方法で使用されることができます。ビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソースがあるファイル名と[リソース識別子](../windows/symbols-resource-identifiers.md)します。 他のユーザー、ダイアログ、メニューのおよび Win32 プロジェクトの文字列テーブルなど存在リソース スクリプト (.rc) ファイルまたはリソース テンプレート (.rct) ファイルの一部としてのみです。

リソースがプロジェクトの外部にも編集できるを参照してください[方法。プロジェクト (スタンドアロン) の外部のリソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

> [!NOTE]
> リソースのプロパティの[プロパティ ウィンドウを使用して変更できる](../windows/changing-the-properties-of-a-resource.md)します。

リソースのプロパティを編集するには。

1. [リソース ビュー](../windows/resource-view-window.md)、編集するリソースを右クリックして**プロパティ**ショートカット メニューから。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)リソースのプロパティを変更します。

リソースのプロパティに加えられた変更を元に戻すには。

1. リソースがフォーカスを必ず**リソース ビュー**します。

1. 選択**を元に戻す**から、**編集**メニュー。

### <a name="win32-resources"></a>Win32 リソース

Win32 リソースにアクセスすることができます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウ。

リソース エディターで Win32 リソースを表示します。

1. 選択**リソース ビュー**から、**ビュー**メニュー。

1. 場合、**リソース ビュー**最上位のウィンドウでは、select 以外のウィンドウ、**リソース ビュー**上部にタブ。

1. **リソース ビュー**、表示するリソースを含むプロジェクトのフォルダーを展開します。 たとえば、ダイアログ リソースを表示する場合は、展開、**ダイアログ**フォルダー。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. たとえば、リソースをダブルクリックして**IDD_ABOUTBOX**します。

   リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースの場合は、リソースで開きます、**ダイアログ**エディター。

   できます[、プロジェクトを開く必要はありません (リソース スクリプト) .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

既存の win32 リソースを削除します。

1. **リソース ビュー**リソースの種類のノードを展開します。

2. 削除するリソースを右クリックして**削除**ショートカット メニューから。

   > [!NOTE]
   > .Rc ファイルをプロジェクトの外部のドキュメント ウィンドウで開いているときに、同じショートカット メニューのコマンドを使用してリソースを削除することができます。

### <a name="resources-in-managed-projects"></a>マネージ プロジェクト内のリソース

マネージ プロジェクトでは、リソース スクリプト ファイルを使用しないためにからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集をサポートされていません。

リソース エディターでマネージ リソースを表示します。

**ソリューション エクスプ ローラー**、たとえば、リソースをダブルクリックして*Bitmap1.bmp*します。

   リソースが適切なエディターで開きます。

既存のマネージ リソースを削除します。

**ソリューション エクスプ ローラー**、削除するリソースを右クリックして**削除**ショートカット メニューから。

## <a name="preview-resources"></a>プレビューのリソース

グラフィカル リソースを開かずに表示できるように、リソースをプレビューします。 プレビューは、リソース識別子を数値に変更されるため、コンパイルした後にも実行可能ファイルの場合に便利です。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューでそれらをすばやく識別できます。

次のリソースの種類の視覚的レイアウトをプレビューできます。ビットマップ、ダイアログ、アイコン、メニューのカーソル、ツールバー

リソースには、ビジュアルのプレビュー機能は適用されません。アクセラレータ、マニフェスト、文字列テーブル、およびバージョン情報

> [!NOTE]
> リソースをプレビューするには、Win32 が必要です。

リソースをプレビューするには。

1. [リソース ビュー](../windows/resource-view-window.md)または、リソースを選択して、ドキュメント ウィンドウ`IDD_ABOUTBOX`します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を選択、**プロパティ ページ**ボタンをクリックします。

   > [!TIP]
   > ショートカットが、上、**ビュー**メニューの **プロパティ ページ**します。

   **プロパティ ページ**リソースが開き、リソースのプレビューを表示します。 使用することができますし、**を**と**ダウン**ツリーを移動する方向キーを制御**リソース ビュー**またはドキュメント ウィンドウ。 **プロパティ ページ**は開いたままにし、フォーカスがあり、プレビューできる任意のリソースを表示します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[シンボル:リソース識別子](../windows/symbols-resource-identifiers.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)