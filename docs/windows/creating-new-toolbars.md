---
title: 新しいツールバーを作成 (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.toolbar
helpviewer_keywords:
- toolbars [C++], creating
- Toolbar editor [C++], creating new toolbars
- Insert Resource
ms.assetid: 1b28264b-0718-4df8-9f65-979805d2efef
ms.openlocfilehash: 3c36579560c78ff77a624e4827df9d6a9302ae57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551308"
---
# <a name="creating-new-toolbars-c"></a>新しいツールバーを作成 (C++)

### <a name="to-create-a-new-toolbar"></a>新しいツールバーを作成するには

1. **リソース**表示、.rc ファイルを右クリックし **リソースの追加**ショートカット メニューから。 (単に右クリックできる場合は、.rc ファイル内の既存のツールバーにある場合は、**ツールバー**フォルダーと選択**挿入ツールバー**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **リソースの追加**ダイアログ ボックスで、**ツールバー**で、**リソースの種類** をクリックし、**新規**します。

   プラス記号の場合 (**+**) 横に表示されます、**ツールバー**リソースの種類ツールバーのテンプレートがあることを意味します。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックします。**新規**します。

   \- または -

3. [ツールバーに既存のビットマップを変換](../windows/converting-bitmaps-to-toolbars.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

MFC または ATL

## <a name="see-also"></a>関連項目

[ツール バー エディター](../windows/toolbar-editor.md)