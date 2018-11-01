---
title: ツール バー エディター (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar.F1
helpviewer_keywords:
- resource editors [C++], Toolbar editor
- editors, toolbars
- toolbars [C++], editing
- Toolbar editor
ms.assetid: aa9f0adf-60f6-4f79-ab05-bc330f15ec43
ms.openlocfilehash: 7efff3d4d784de6ee3130c3481f3674351cc7463
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486057"
---
# <a name="toolbar-editor-c"></a>ツール バー エディター (C++)

**ツールバー**エディターでは、C++ のツールバーのリソースを作成し、ビットマップをツール バー リソースに変換することができます。 **ツールバー**エディターでは、グラフィカルな表示を使用して、ツールバーとほぼ同じに完成したアプリケーションでどのように表示されるがボタンを表示します。

**ツールバー**エディターができます。

- [新しいツールバーとボタンを作成する](../windows/creating-new-toolbars.md)

- [ビットマップからツールバーのリソースに変換する](../windows/converting-bitmaps-to-toolbars.md)

- [ツールバー ボタンを作成、移動、編集する](../windows/creating-moving-and-editing-toolbar-buttons.md)

- [ツール ヒントを作成する](../windows/creating-a-tool-tip-for-a-toolbar-button.md)

**ツールバー**エディター ウィンドウには、イメージ エディター ウィンドウと同じボタンのイメージの 2 つのビューが表示されます。 分割バーは、2 つのペインを分割します。 分割バーを左右にドラッグすると、ペインの相対サイズを変更できます。 アクティブなペインには、選択境界線が表示されます。 イメージの 2 つのビューの上にはサブジェクト ツールバーがあります。

![ツール バー エディター](../mfc/media/vctoolbareditor.gif "vcToolbarEditor")ツール バー エディター

**ツールバー**エディターと似ています、**イメージ**エディターの機能です。 メニュー項目、グラフィック ツール、およびビットマップのグリッドは、内のものと同じ、**イメージ**エディター。 メニュー コマンドでは、**イメージ**メニュー間を切り替えることができるように、**ツールバー**エディターと**イメージ**エディター。 使用しての詳細については、**グラフィックス**ツールバーで、**色**パレット、または**イメージ**] メニューの [を参照してください[イメージ エディター](../windows/image-editor-for-icons.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[リソース エディター](../windows/resource-editors.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)