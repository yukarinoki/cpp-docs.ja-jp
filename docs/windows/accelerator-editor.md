---
title: アクセラレータ エディター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [Visual Studio], accelerator key
- accelerator keys
- resource editors, Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e5ce1fcd71f6f49532d083c7cb2dcfce9ed644c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856418"
---
# <a name="accelerator-editor"></a>アクセラレータ エディター
アクセラレータ テーブルは、アクセス キー (ショートカット キーとも呼ばれます) とそれらに関連付けられたコマンド識別子の一覧を含む Windows リソースです。 プログラムは複数のアクセラレータ テーブルを持つことができます。  
  
 通常、アクセラレータはメニューやツール バーでも使用できるプログラム コマンドのキーボード ショートカットとして使用されます。 しかし、アクセラレータ テーブルを使用すると、関連付けられているユーザー インターフェイス オブジェクトのないコマンドにキーの組み合わせを定義できます。  
  
 [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) を使用して、コードにアクセス キーのコマンドをフックできます。  
  
 アクセラレータ エディターでは、次の操作ができます。  
  
-   [アクセラレータ プロパティの設定](../windows/setting-accelerator-properties.md)  
  
-   [アクセス キーとメニュー項目との関連付け](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)  
  
-   [定義済みのアクセス キーの使用](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  アクセラレータ エディターの使用中、右クリックすると、頻繁に使用するコマンドのショートカット メニューを表示できます。 使用できるコマンドは、ポインターの位置によって異なります。  
  
    > [!NOTE]
    >  Windows では、空のアクセラレータ テーブルは作成できません。 エントリがないアクセラレータ テーブルを作成すると、テーブルを保存する際に自動的に削除されます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)

