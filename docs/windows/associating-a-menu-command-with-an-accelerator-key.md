---
title: メニュー コマンドとアクセラレータ キー (C++) の関連付け |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b55535e9306d272d47f098e7cf15d28a764f3620
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316290"
---
# <a name="associating-a-menu-command-with-an-accelerator-key-c"></a>メニュー コマンドとアクセラレータ キー (C++) の関連付け

メニュー コマンドとキーボードの組み合わせで同じプログラム コマンドを発行したいと思うことはよくあります。 使用してこれを行う、**メニュー**エディター メニュー コマンドをアプリケーションのアクセラレータ テーブル内のエントリに同じリソース識別子を割り当てできます。 次に、メニュー コマンドの [キャプション](../windows/menu-command-properties.md) を編集して、アクセラレータ キーの名前を表示します。

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>メニュー コマンドをアクセラレータ キーと関連付けるには

1. **メニュー** エディターで、目的のメニュー コマンドを選択します。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)で、アクセラレータ キーの名前を **キャプション** プロパティに追加します。

   - メニューのキャプションに続いて、タブ (\t) のエスケープ シーケンスを入力し、すべてのメニューのアクセラレータ キーが左揃えされるようにします。

   - 修飾子キーの名前を入力 (**Ctrl**、 **Alt**、または**Shift**) プラス記号 (**+**) と名前、文字、または追加のキーの記号です。

       割り当てるにはたとえば、 **Ctrl**+**O**を**オープン**コマンドを**ファイル**] メニューの [メニュー コマンドを変更します。**キャプション**次のように見えるようにします。

        ```
        &Open...\tCtrl+O
        ```

       メニュー コマンド、**メニュー**エディターは、入力すると、新しいキャプションを反映するように更新されます。

3. [アクセラレータ](../windows/adding-an-entry-to-an-accelerator-table.md) エディターで **アクセラレータ テーブル エントリ** を作成し、メニュー コマンドと同じ識別子をそれに割り当てます。 使用するキーの組み合わせは、覚えやすいものにしてください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[メニューへのコマンドの追加](../windows/adding-commands-to-a-menu.md)  
[メニュー エディター](../windows/menu-editor.md)