---
title: 表示して、リソース エディター (C++) でのリソースの編集
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
ms.openlocfilehash: 02ab58d37f3f188c3d65740b218cb9b2ac799714
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742662"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor-c"></a>表示して、リソース エディター (C++) でのリソースの編集

各リソースの種類が、**リソース**そのリソースの種類に固有のエディター。 再配置してサイズ変更、コントロールと機能を追加するか、またはそれ以外の場合、関連付けられているエディターを使用してリソースの側面を変更できます。 内のリソースを編集することもできます。[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)と[バイナリ形式](../windows/opening-a-resource-for-binary-editing.md)します。

リソースの種類によっては個々 のファイルをインポートしてさまざまな方法で使用されることができます。ビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソースがあるファイル名と[リソース識別子](../windows/symbols-resource-identifiers.md)します。 他のユーザー、ダイアログ、メニューのおよび Win32 プロジェクトの文字列テーブルなど存在リソース スクリプト (.rc) ファイルまたはリソース テンプレート (.rct) ファイルの一部としてのみです。

> [!NOTE]
> リソースのプロパティの[プロパティ ウィンドウを使用して変更できる](../windows/changing-the-properties-of-a-resource.md)します。

## <a name="win32-resources"></a>Win32 リソース

Win32 リソースにアクセスすることができます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウ。

### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>リソース エディターで、Win32 リソースを表示するには

1. 選択**リソース ビュー**から、**ビュー**メニュー。

1. 場合、**リソース ビュー**最上位のウィンドウでは、select 以外のウィンドウ、**リソース ビュー**上部にタブ。

1. **リソース ビュー**、表示するリソースを含むプロジェクトのフォルダーを展開します。 たとえば、ダイアログ リソースを表示する場合は、展開、**ダイアログ**フォルダー。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. たとえば、リソースをダブルクリックして**IDD_ABOUTBOX**します。

   リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースの場合は、リソースで開きます、**ダイアログ**エディター。

   できます[、プロジェクトを開く必要はありません (リソース スクリプト) .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。

### <a name="to-delete-an-existing-win-32-resource"></a>既存の win32 リソースを削除するには

1. **リソース ビュー**リソースの種類のノードを展開します。

2. 削除するリソースを右クリックして**削除**ショートカット メニューから。

   > [!NOTE]
   > .Rc ファイルをプロジェクトの外部のドキュメント ウィンドウで開いているときに、同じショートカット メニューのコマンドを使用してリソースを削除することができます。

## <a name="resources-in-managed-projects"></a>マネージ プロジェクト内のリソース

マネージ プロジェクトでは、リソース スクリプト ファイルを使用しないためにからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集をサポートされていません。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>リソース エディターでマネージ リソースを表示するには

**ソリューション エクスプ ローラー**、たとえば、リソースをダブルクリックして**Bitmap1.bmp**します。

   リソースが適切なエディターで開きます。

### <a name="to-delete-an-existing-managed-resource"></a>既存のマネージ リソースを削除するには

**ソリューション エクスプ ローラー**、削除するリソースを右クリックして**削除**ショートカット メニューから。

## <a name="changing-the-properties-of-resources"></a>リソースのプロパティを変更します。

### <a name="to-edit-the-properties-of-a-resource"></a>リソースのプロパティを変更するには

1. [リソース ビュー](../windows/resource-view-window.md)、編集するリソースを右クリックして**プロパティ**ショートカット メニューから。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)リソースのプロパティを変更します。

### <a name="to-undo-a-change-made-to-the-properties-of-a-resource"></a>リソースのプロパティに加えられた変更を元に戻す

1. リソースがフォーカスを必ず**リソース ビュー**します。

1. 選択**を元に戻す**から、**編集**メニュー。

## <a name="previewing-resources"></a>リソースのプレビュー

グラフィカル リソースを開かずに表示できるように、リソースをプレビューします。 プレビューは、リソース識別子を数値に変更されるため、コンパイルした後にも実行可能ファイルの場合に便利です。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューでそれらをすばやく識別できます。

次のリソースの種類の視覚的レイアウトをプレビューできます。

- ビットマップ

- ダイアログ

- アイコン

- メニュー

- カーソル

- ツール バー

ビジュアルのプレビュー機能は、アクセラレータ、マニフェスト、文字列テーブル、およびバージョン情報リソースに適用されません。

### <a name="to-preview-resources"></a>リソースをプレビューするには

1. [リソース ビュー](../windows/resource-view-window.md)または、リソースを選択して、ドキュメント ウィンドウ**IDD_ABOUTBOX**します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

1. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を選択、**プロパティ ページ**ボタンをクリックします。

   \- または -

   **ビュー**メニューの **プロパティ ページ**します。

   **プロパティ ページ**リソースが開き、リソースのプレビューを表示します。 使用することができますし、**を**と**ダウン**ツリーを移動する方向キーを制御**リソース ビュー**またはドキュメント ウィンドウ。 **プロパティ ページ**は開いたままにし、フォーカスがあり、プレビューできる任意のリソースを表示します。

> [!NOTE]
> リソースをプレビューするには、Win32 が必要です。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[リソース エディター](../windows/resource-editors.md)