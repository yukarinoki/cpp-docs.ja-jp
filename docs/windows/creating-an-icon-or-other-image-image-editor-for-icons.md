---
title: アイコンまたはその他のイメージの作成 (アイコン用イメージ エディター)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
ms.openlocfilehash: 45a119114c26513788b2cdc134e4258e42cf896d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503288"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>アイコンまたはその他のイメージの作成 (アイコン用イメージ エディター)

新しいイメージ (ビットマップ、アイコン、カーソル、またはツールバー) を作成し、イメージ エディターを使用して、その外観をカスタマイズすることができます。 後でパターン化、新しいビットマップを作成することも、[テンプレート](../windows/how-to-use-resource-templates.md)します。

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>アンマネージの C++ プロジェクトに新しいイメージ リソースを追加するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし**リソースの挿入**ショートカット メニューからです。 (を単に右クリックなど、カーソル、.rc ファイルに既存のイメージ リソースが既にある場合、**カーソル**フォルダーと選択**挿入カーソル**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. [リソースの挿入 ダイアログ ボックス](../windows/add-resource-dialog-box.md)、作成するには、イメージ リソースの種類を選択します (**ビットマップ**、たとえば) をクリックして**新規**。

   プラス記号の場合 (**+**) でイメージ リソースの種類の横に表示、**リソースの挿入**ダイアログ ボックスで、ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックします。**新規**します。

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>.NET のプログラミング言語のプロジェクトに新しいイメージ リソースを追加するには

1. **ソリューション エクスプ ローラー**、プロジェクト フォルダーを右クリックし (たとえば、 `WindowsApplication1`)。

2. ショートカット メニューでは、次のようにクリックします。**追加**、を選択し、**新しい項目の追加**します。

3. **カテゴリ**ウィンドウで、展開、**ローカル プロジェクト アイテム**フォルダーを選択し、**リソース**します。

4. **テンプレート**ウィンドウで、プロジェクトに追加するには、リソースの種類を選択します。

   プロジェクトにリソースを追加**ソリューション エクスプ ローラー**され、リソースがで、[イメージ エディター](../windows/image-editor-for-icons.md)します。 イメージ エディターで使用できるすべてのツールを使用して、イメージを変更することができますようになりました。 マネージ プロジェクトにイメージを追加する方法の詳細については、次を参照してください。[デザイン時にピクチャの読み込み](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms)します。

   > [!NOTE]
   > 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。 詳細については、次を参照してください。[リソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)で、 *.NET Framework 開発者ガイド*します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

なし

## <a name="see-also"></a>関連項目

[アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[ビットマップからツール バーへの変換](../windows/converting-bitmaps-to-toolbars.md)<br/>
[ツール バーの新規作成](../windows/creating-new-toolbars.md)<br/>
[グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[アイコン用イメージ エディター](../windows/image-editor-for-icons.md)