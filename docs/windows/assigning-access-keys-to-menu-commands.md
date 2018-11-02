---
title: メニュー コマンド (C++) へのアクセス キーの割り当てください。
ms.date: 11/04/2016
helpviewer_keywords:
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
ms.openlocfilehash: 7a3302f7744bf5c3a0cbaac96de04d9f649fac10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587331"
---
# <a name="assigning-access-keys-to-menu-commands-c"></a>メニュー コマンド (C++) へのアクセス キーの割り当てください。

C++ プロジェクトで、メニューとメニュー コマンドにアクセス キー (ユーザーがキーボードを使用してメニューを選択できるようにするニーモニック) を割り当てることができます。

### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>メニュー コマンドにアクセス (ショートカット) キーを割り当てるには

1. アンパサンドを入力 (`&`) メニュー名やコマンド名、対応するアクセス キーとしてその文字を指定する文字の前にします。 たとえば"& File"セット**Alt**+**F**のショートカット キーとして、**ファイル**Microsoft Windows 用に記述されたアプリケーションでメニュー。

   メニュー項目は、文字の 1 つがショートカット キーに割り当てられている表示可能キューを提供します。 アンパーサンドに続く文字は、下線付きで表示されます (オペレーティング システムによって異なる)。

   > [!NOTE]
   > メニューを右クリックし、ショートカット メニューから **[ニーモニックの確認]** を選択して、メニューのすべてのアクセスキーが一意であることを確認してください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[メニュー エディター](../windows/menu-editor.md)