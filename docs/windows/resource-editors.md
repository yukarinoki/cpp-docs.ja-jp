---
title: リソースエディター (C++)
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
ms.openlocfilehash: 2552f9eea79aa0a3545d9746d85cacfbd9a3f25d
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353169"
---
# <a name="resource-editors-c"></a>リソースエディター (C++)

リソースエディターは、Visual Studio プロジェクトに含まれるリソースを作成または変更するための特殊な環境です。 Visual Studio のリソース エディターでは、アプリケーションのリソースをすばやく簡単に作成して変更できるようにする技術とインターフェイスを共有します。 リソース エディターを使用すると、リソースを適切なエディターで表示して編集でき、リソースをプレビューすることができます。

リソースを作成したり開いたりすると、適切なエディターが自動的に開きます。

> [!NOTE]
> マネージプロジェクトではリソーススクリプトファイルを使用しないため、 **ソリューションエクスプローラー**からリソースを開く必要があります。 [イメージエディター](../windows/image-editor-for-icons.md)と[バイナリエディター](binary-editor.md)を使用して、マネージプロジェクトのリソースファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

|使用|編集|
|----------------|----------------|
|[アクセラレータエディター](../windows/accelerator-editor.md)|Visual Studio C++ プロジェクトのアクセラレータテーブル。|
|[バイナリエディター](binary-editor.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのバイナリ データの情報およびカスタム リソース。|
|[ダイアログエディター](../windows/dialog-editor.md)|Visual Studio C++ プロジェクトのダイアログボックス。|
|[イメージエディター](../windows/image-editor-for-icons.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのビットマップ、アイコン、カーソル、およびその他のイメージ ファイル。|
|[メニューエディター](../windows/menu-editor.md)|Visual Studio C++ プロジェクトのメニューリソース。|
|[Ribbon エディター](../mfc/ribbon-designer-mfc.md)|MFC プロジェクトのリボン リソース。|
|[文字列エディター](../windows/string-editor.md)|Visual Studio C++ プロジェクトの文字列テーブル。|
|[ツールバーエディター](../windows/toolbar-editor.md)|Visual Studio C++ プロジェクトのツールバーリソース。 **ツールバーエディター**は、**イメージエディター**の一部です。|
|[バージョン情報エディター](../windows/version-information-editor.md)|Visual Studio C++ プロジェクトのバージョン情報。|

> [!NOTE]
> プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [方法: リソースを作成する](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

## <a name="view-and-edit-resources"></a>リソースの表示と編集

各リソースの種類には、そのリソースの種類に固有のリソースエディターがあります。 関連するエディターを使用して、コントロールや機能の再配置、サイズ変更、追加、またはリソースの側面の変更を行うことができます。 また、テキスト形式とバイナリ形式でリソースを編集することもできます。 詳細については、「 [方法: リソースを作成する](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

一部のリソースの種類は、さまざまな方法でインポートして使用できる個別のファイルです。これには、ビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソースには、ファイル名と [リソース識別子](../windows/symbols-resource-identifiers.md)があります。 他のダイアログ、メニュー、Win32 プロジェクトの文字列テーブルなどは、リソーススクリプト (.rc) ファイルまたはリソーステンプレート (.rct) ファイルの一部としてのみ存在します。

また、プロジェクトを開かずに、プロジェクトの外部でリソースを編集することもできます。 詳細については、「 [方法: リソースを作成する](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)」を参照してください。

> [!NOTE]
> リソースのプロパティは、[ **プロパティ** ] ウィンドウを使用して変更できます。

- リソースのプロパティを編集するには、 [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)で、編集するリソースを右クリックし、[ **プロパティ**] を選択します。  次に、 [プロパティウィンドウ](/visualstudio/ide/reference/properties-window)で、リソースのプロパティを変更します。

- リソースのプロパティに対する変更を元に戻すには、リソースが**リソースビュー**にフォーカスしていることを確認し、[**編集**] メニューの [**元に戻す**] をクリックします。

### <a name="win32-resources"></a>Win32 リソース

Win32 リソースには、[ [リソースビュー](how-to-create-a-resource-script-file.md#create-resources) ] ウィンドウでアクセスできます。

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>リソースエディターで Win32 リソースを表示するには

1. [メニューの**表示**] [  >  **その他のウィンドウ**  >  **リソースビュー**] を表示します。

1. **リソースビュー**ウィンドウが一番上のウィンドウではない場合は、[**リソースビュー** ] タブを選択して一番上に移動します。

1. **リソースビュー**から、表示するリソースが含まれているプロジェクトのフォルダーを展開します。 たとえば、ダイアログリソースを表示する場合は、 **ダイアログ** フォルダーを展開します。

1. リソース ( **IDD_ABOUTBOX**など) をダブルクリックします。

   リソースが適切なエディターで開きます。 たとえば、ダイアログリソースの場合は、 **ダイアログエディター**内でリソースが開きます。

#### <a name="to-delete-an-existing-win32-resource"></a>既存の Win32 リソースを削除するには

1. **リソースビュー**で、リソースの種類のノードを展開します。

1. 削除するリソースを右クリックし、[ **削除**] を選択します。

> [!TIP]
> このメソッドは、プロジェクトの外部のドキュメントウィンドウで .rc ファイルを開いている場合にも使用できます。

### <a name="managed-project-resources"></a>マネージプロジェクトリソース

マネージプロジェクトはリソーススクリプトファイルを使用しないため、 **ソリューションエクスプローラー**からリソースを開く必要があります。 [イメージエディター](../windows/image-editor-for-icons.md)と[バイナリエディター](binary-editor.md)を使用して、マネージプロジェクトのリソースファイルを操作します。 編集するマネージリソースは、リンクされたリソースである必要があります。また、Visual Studio リソースエディターは、埋め込みリソースの編集をサポートしていません。

- リソースエディターでマネージリソースを表示するには、 **ソリューションエクスプローラー**で、リソース (たとえば *Bitmap1.bmp*) をダブルクリックすると、適切なエディターでリソースが開きます。

- 既存のマネージリソースを削除するには、 **ソリューションエクスプローラー**で、削除するリソースを右クリックし、[ **削除**] を選択します。

## <a name="preview-resources"></a>リソースのプレビュー

リソースをプレビューして、グラフィカルリソースを開くことなく表示できるようにします。 また、リソース識別子が数値に変更されるため、コンパイル後の実行可能ファイルにもプレビューが役立ちます。 多くの場合、これらの数値識別子は十分な情報を提供しないため、リソースのプレビューを使用すると、リソースを簡単に識別できます。

次のリソースの種類では、ビジュアルレイアウトプレビューが提供されています: ビットマップ、ダイアログ、アイコン、メニュー、カーソル、ツールバー

次のリソースは、visual preview を提供していません: アクセラレータ、マニフェスト、文字列テーブル、バージョン情報

> [!NOTE]
> リソースをプレビューするには Win32 が必要です。

### <a name="to-preview-resources"></a>リソースをプレビューするには

1. [リソースビュー](how-to-create-a-resource-script-file.md#create-resources)またはドキュメントウィンドウで、リソース (たとえば、 **IDD_ABOUTBOX**) を選択します。

1. [プロパティウィンドウ](/visualstudio/ide/reference/properties-window)で、[**プロパティページ**] ボタンを選択します。

   > [!TIP]
   > ショートカットを使用し、メニュー**ビュー**の [  >  **プロパティページ**] を表示します。

   リソースの **プロパティ** ページが開き、そのリソースのプレビューが表示されます。 **上**方向キーと**下**方向キーを使用して、**リソースビュー**またはドキュメントウィンドウのツリーコントロールを移動できます。 **プロパティ**ページは開いたままになり、フォーカスがあり、プレビューできるリソースが表示されます。

## <a name="requirements"></a>必要条件

None

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソースファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
