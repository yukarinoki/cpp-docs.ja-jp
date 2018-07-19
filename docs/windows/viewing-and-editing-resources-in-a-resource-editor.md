---
title: 表示して、リソース、リソース エディターで編集 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resourceview
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- Resource View pane
- layouts, previewing resource
- code, viewing resources
- resource editors, viewing resources
- .rc files, viewing resources
- resources [Visual Studio], editing
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1afa1377b222789243706cf3c5e61f45b4fcd1a1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891819"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>リソース エディターでのリソースの表示と編集
各リソースの種類には、そのリソースの種類に固有のリソース エディターがあります。 再配置してサイズを変更する、コントロールや機能を追加するか、またはそれ以外の場合、関連付けられているエディターを使用してリソースの側面を変更できます。 内のリソースを編集することもできます。[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)と[バイナリ形式](../windows/opening-a-resource-for-binary-editing.md)です。  
  
 リソースの種類によっては、インポートしてさまざまな方法で使用できる個々 のファイルビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソースがファイルの名前を持つだけでなく[リソース識別子](../windows/symbols-resource-identifiers.md)です。 他のユーザー、ダイアログ ボックス、メニューのおよび Win32 プロジェクト内の文字列テーブルなどとしてのみ存在するリソース スクリプト (.rc) ファイルまたはリソース テンプレート (.rct) ファイルの一部です。  
  
> [!NOTE]
>  リソースのプロパティの[プロパティ ウィンドウを使用して変更できる](../windows/changing-the-properties-of-a-resource.md)です。  
  
## <a name="win32-resources"></a>Win32 リソース  
 Win32 のリソースにアクセスすることができます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウです。  
  
#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>リソース エディターで Win32 リソースを表示するには  
  
1.  選択**リソース ビュー**から、**ビュー**メニュー。  
  
2.  リソース ビュー ウィンドウが最上位のウィンドウではない場合にクリックして、**リソース ビュー**上部にタブです。  
  
3.  リソース ビューを表示するリソースを含むプロジェクトのフォルダーを展開します。 たとえば、ダイアログ リソースを表示する場合は、ダイアログ フォルダーを展開します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
4.  リソースを IDD_ABOUTBOX をダブルクリックします。  
  
     リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースの場合は、ダイアログ エディター内にリソースが開きます。  
  
     こともできます[しなくても、プロジェクトを開く (リソース スクリプト) .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)です。  
  
#### <a name="to-delete-an-existing-win-32-resource"></a>既存の win32 リソースを削除するには  
  
1.  リソース ビューで、リソースの種類のノードを展開します。  
  
2.  削除するリソースを右クリックして**削除**ショートカット メニューからです。  
  
    > [!NOTE]
    >  プロジェクトの外部のドキュメント ウィンドウで開く、.rc ファイルがある場合は、同じショートカット メニューのコマンドを使用してリソースを削除することができます。  
  
## <a name="resources-in-managed-projects"></a>マネージ プロジェクト内のリソース  
 マネージ プロジェクトでは、リソース スクリプト ファイルは使用しないのでからリソースを開く必要があります**ソリューション エクスプ ローラー**です。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
#### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>リソース エディターでマネージ リソースを表示するには  
  
1.  ソリューション エクスプ ローラーで、リソース、たとえば、Bitmap1.bmp をダブルクリックします。  
  
     リソースが適切なエディターで開きます。  
  
#### <a name="to-delete-an-existing-managed-resource"></a>既存のマネージ リソースを削除するには  
  
1.  ソリューション エクスプ ローラーで、削除するリソースを右クリックして**削除**ショートカット メニューからです。  
  
### <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)

