---
title: 新しいダイアログ ボックス (C++) の作成
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
ms.openlocfilehash: ed1bb21029b2a61eb51b54386ed51ef08b90e149
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605335"
---
# <a name="creating-a-new-dialog-box-c"></a>新しいダイアログ ボックス (C++) の作成

### <a name="to-create-a-new-dialog-box"></a>新しいダイアログ ボックスを作成するには

1. [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし **リソースの追加**ショートカット メニューからです。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **リソースの追加**ダイアログ ボックスで、**ダイアログ**で、**リソースの種類** をクリックし、**新規**します。

   プラス記号の場合 (**+**) 横に表示されます、**ダイアログ**ダイアログ ボックスのテンプレートが使用できることを意味、リソースの種類。 テンプレートの一覧を展開し、テンプレートを選択してをクリックするには、プラス記号をクリックします。**新規**します。

   新しいダイアログ ボックスが開き、**ダイアログ**エディター。

   できます[の編集 ダイアログ ボックスのエディターで既存のダイアログ ボックスを開く](../windows/viewing-and-editing-resources-in-a-resource-editor.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[方法: リソースを作成する](../windows/how-to-create-a-resource.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[ダイアログ エディター](../windows/dialog-editor.md)