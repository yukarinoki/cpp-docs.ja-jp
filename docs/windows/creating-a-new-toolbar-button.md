---
title: 新しいツール バー ボタン (C++) を作成します。
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
ms.openlocfilehash: 1fe3e960ea9d2cec36e1c0d1ee9edb30bcc354d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512503"
---
# <a name="creating-a-new-toolbar-button-c"></a>新しいツール バー ボタン (C++) を作成します。

### <a name="to-create-a-new-toolbar-button"></a>新しいツール バー ボタンを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)リソース フォルダー (Project1.rc など) を展開します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 展開、**ツールバー**フォルダーと編集にツールバーを選択します。

3. ツールバーの右端にある空白のボタンに ID を割り当てます。 編集することによって行うことができます、 **ID**プロパティ、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 たとえば、ツール バー ボタンにメニュー オプションと同じ ID を提供したい場合があります。 この場合、ドロップダウン リスト ボックスを使用して、 **ID**のメニュー オプション。

   - または -

   ツールバーの右端にある空白のボタンを選択します (で、**ツールバーのビュー**ウィンドウ) と描画を開始します。 既定のボタンのコマンド ID が割り当てられます (ID_BUTTON\<n >)。

コピーして、新しいボタンのツールバー上にイメージを貼り付けることができます。

### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>ツールバーにボタンとしてイメージを追加するには

1. [リソース ビュー](../windows/resource-view-window.md)ツールバーをダブルクリックして開きます。

2. 次に、ツールバーに追加するには、イメージを開きます。

   > [!NOTE]
   > Visual Studio で、イメージを開く場合で開きます、**イメージ**エディター。 他のグラフィックス プログラムでイメージを開くこともできます。

3. **編集**] メニューの [選択**コピー**します。

4. ソース ウィンドウの上部にあるタブをクリックして、ツールバーに切り替えます。

5. **編集**] メニューの [選択**貼り付け**します。

   イメージは、ツールバーの [新規] ボタンとして表示されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[ツール バー ボタンのプロパティ](../windows/toolbar-button-properties.md)<br/>
[ツール バー ボタンの作成、移動、および編集](../windows/creating-moving-and-editing-toolbar-buttons.md)<br/>
[ツール バー エディター](../windows/toolbar-editor.md)