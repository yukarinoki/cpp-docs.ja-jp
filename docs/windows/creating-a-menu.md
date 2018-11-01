---
title: メニュー (C++) の作成
ms.date: 11/04/2016
f1_keywords:
- vc.editors.menu
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
ms.openlocfilehash: b779e6b089410b818247471086fe987c37b1f36c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518557"
---
# <a name="creating-a-menu-c"></a>メニュー (C++) の作成

> [!NOTE]
> **リソース ウィンドウ**Express エディションでは使用できません。

### <a name="to-create-a-standard-menu"></a>標準メニューを作成するには

1. **[表示]** メニューの **[リソース ビュー]** をクリックし、 **[メニュー]** 見出しを右クリックし、 **[リソースの追加]** をクリックします。 **[メニュー]** をクリックします。

2. メニュー バーで、"ここへ入力" と表示されている四角形の **[新しい項目]** ボックスを選びます。

   ![メニュー エディターの新しい項目ボックス](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")<br/>
   [新しい項目] ボックス

3. たとえば「ファイル」など、新しいメニューの名前を入力します。

   入力したテキストは、 **メニュー** エディターと、 **プロパティ ウィンドウ** の [[キャプション]](/visualstudio/ide/reference/properties-window)ボックスの両方に表示されます。 新しいメニューのプロパティはこのどちらからでも編集できます。

   メニュー バーで新しいメニューの名前を指定すると、さらに別のメニューを追加できるように [新しい項目] ボックスが右に移動し、最初のメニューの下に新しい [新しい項目] ボックスが表示されます。この新しいボックスでメニュー コマンドを追加できます。

   ![展開された 新しい項目ボックス](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")<br/>
   メニュー名の入力後にフォーカスが移動した [新しい項目] ボックス

   > [!NOTE]
   > メニュー バーの単一項目のメニューを作成するには、設定、**ポップアップ**プロパティを**False**します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[メニュー エディター](../windows/menu-editor.md)