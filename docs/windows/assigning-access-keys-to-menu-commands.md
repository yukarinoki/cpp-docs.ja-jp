---
title: メニュー コマンドに対するアクセス キーの割り当て |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44a21e5930d0d8f2fcaad79cc5cef5bc984ad8b5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857900"
---
# <a name="assigning-access-keys-to-menu-commands"></a>メニュー コマンドに対するアクセス キーの割り当て
メニューとメニュー コマンドにアクセス キー (ユーザーがキーボードを使ってメニューを選択できるようにするニーモニック) を割り当てることができます。  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>メニュー コマンドにアクセス (ショートカット) キーを割り当てるには  
  
1.  メニュー名やコマンド名の文字の前にアンパサンド (**&**) を入力し、対応するアクセス キーとしてその文字を指定します。 たとえば、"&File" は ALT+F を、Microsoft Windows で作成されるアプリケーションの [File] メニューのショートカット キーとして設定します。  
  
     メニュー項目は、文字の 1 つがショートカット キーに割り当てられている表示可能キューを提供します。 アンパーサンドに続く文字は、下線付きで表示されます (オペレーティング システムによって異なる)。  
  
    > [!NOTE]
    >  メニューを右クリックし、ショートカット メニューから **[ニーモニックの確認]** を選択して、メニューのすべてのアクセスキーが一意であることを確認してください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [メニュー エディター](../windows/menu-editor.md)