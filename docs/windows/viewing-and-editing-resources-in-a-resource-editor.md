---
title: 表示と編集リソース エディターでのリソース |Microsoft Docs
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
ms.openlocfilehash: 5fca755c46d3fc5628adc2c724b9307a346d1fe7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014004"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>リソース エディターでのリソースの表示と編集
各リソースの種類が、**リソース**そのリソースの種類に固有のエディター。 再配置してサイズ変更、コントロールと機能を追加するか、またはそれ以外の場合、関連付けられているエディターを使用してリソースの側面を変更できます。 内のリソースを編集することもできます。[テキスト形式](../windows/how-to-open-a-resource-script-file-in-text-format.md)と[バイナリ形式](../windows/opening-a-resource-for-binary-editing.md)します。  
  
 リソースの種類によっては個々 のファイルをインポートしてさまざまな方法で使用されることができます。ビットマップ、アイコン、カーソル、ツールバー、および html ファイルが含まれます。 このようなリソース ファイル名があるだけでなく[リソース識別子](../windows/symbols-resource-identifiers.md)します。 他のユーザー、ダイアログ、メニューのおよび Win32 プロジェクトの文字列テーブルなど存在リソース スクリプト (.rc) ファイルまたはリソース テンプレート (.rct) ファイルの一部としてのみです。  
  
> [!NOTE]
>  リソースのプロパティの[プロパティ ウィンドウを使用して変更できる](../windows/changing-the-properties-of-a-resource.md)します。  
  
## <a name="win32-resources"></a>Win32 リソース  
 Win32 リソースにアクセスすることができます、[リソース ビュー](../windows/resource-view-window.md)ウィンドウ。  
  
### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>リソース エディターで、Win32 リソースを表示するには  
  
1.  選択**リソース ビュー**から、**ビュー**メニュー。  
  
2.  場合、**リソース ビュー**ウィンドウが最上位のウィンドウではありません、クリックして、**リソース ビュー**上部にタブ。  
  
3.  **リソース ビュー**、表示するリソースを含むプロジェクトのフォルダーを展開します。 たとえば、ダイアログ リソースを表示する場合は、展開、**ダイアログ**フォルダー。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
4.  たとえば、リソースをダブルクリックして**IDD_ABOUTBOX**します。  
  
     リソースが適切なエディターで開きます。 たとえば、ダイアログ リソースの場合は、リソースで開きます、**ダイアログ**エディター。  
  
     できます[、プロジェクトを開く必要はありません (リソース スクリプト) .rc ファイル内のリソースを表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。  
  
### <a name="to-delete-an-existing-win-32-resource"></a>既存の win32 リソースを削除するには  
  
1.  **リソース ビュー**リソースの種類のノードを展開します。  
  
2.  削除するリソースを右クリックして**削除**ショートカット メニューから。  
  
    > [!NOTE]
    >  .Rc ファイルをプロジェクトの外部のドキュメント ウィンドウで開いているときに、同じショートカット メニューのコマンドを使用してリソースを削除することができます。  
  
## <a name="resources-in-managed-projects"></a>マネージ プロジェクト内のリソース  
 マネージ プロジェクトでは、リソース スクリプト ファイルは使用しないのでからリソースを開く必要があります**ソリューション エクスプ ローラー**します。 
  [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>リソース エディターでマネージ リソースを表示するには  
  
1.  **ソリューション エクスプ ローラー**、たとえば、リソースをダブルクリックして**Bitmap1.bmp**します。  
  
     リソースが適切なエディターで開きます。  
  
### <a name="to-delete-an-existing-managed-resource"></a>既存のマネージ リソースを削除するには  
  
1.  **ソリューション エクスプ ローラー**、削除するリソースを右クリックして**削除**ショートカット メニューから。  
  
## <a name="requirements"></a>要件  
 なし  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)