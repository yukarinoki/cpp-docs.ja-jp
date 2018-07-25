---
title: リソース ファイル (Visual Studio) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio]
- .rc files
- resource files
- resource script files
- resource script files, Win-32 based applications
- resource script files, files updated when editing resources
- resources [Visual Studio], types of resource files
- rct files
- resources [C++]
- rc files
- resource files, types of
- .rct files
- resource script files, unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b4b56d1f329aee29c37b15590729074d305f04d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879875"
---
# <a name="resource-files-visual-studio"></a>リソース ファイル (Visual Studio)
> [!NOTE]
>  これは Windows デスクトップ アプリケーションだけに適用できます。 ユニバーサル Windows プラットフォーム アプリでリソースについては、次を参照してください。[アプリ リソースの定義](http://msdn.microsoft.com/en-us/476ea844-632c-4467-9ce3-966be1350dd4)です。  
>   
> マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
>  
> .NET プログラミング言語のプロジェクトでは、リソース スクリプト ファイルは使用しないため、 **ソリューション エクスプローラー**」をご覧ください。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
 "リソース ファイル" という用語は、次のようなさまざまな種類のファイルを示します。  
  
-   プログラムのリソース スクリプト (.rc) ファイル。  
  
-   リソース テンプレート (.rct) ファイル。  
  
-   ビットマップ、アイコン、カーソル ファイルなど、スタンドアロン ファイルとして存在し、.rc ファイルから参照される個別のリソース。  
  
-   Resource.h など、開発環境で生成され、.rc ファイルから参照されるヘッダー ファイル。  
  
 リソースは、.exe、.dll、.res ファイルなど、 [その他の種類のファイル](../windows/editable-file-types-for-resources.md) にも存在します。 リソースとリソース ファイルはプロジェクト内から操作できます。また、現在のプロジェクトの一部でないリソースとリソース ファイルも操作できます。 また、Visual Studio の開発環境で作成されたのではないリソース ファイルも操作できます。 たとえば、次のように操作できます。  
  
-   入れ子になっていて、条件付きでインクルードされるリソース ファイルの操作。  
  
-   既存のリソースの更新、または Visual C++ 形式への変換。  
  
-   グラフィック リソースを現在のリソース ファイルとの間でインポートまたはエクスポートする。  
  
-   開発環境では変更できない共有または読み取り専用識別子 (シンボル) のインクルード。  
  
-   複数のプロジェクト間で共有されるリソースなど、現在のプロジェクトで編集を必要としない (または編集したくない) 実行可能 (.exe) ファイル内のリソースのインクルード。  
  
-   開発環境でサポートされていない種類のリソースのインクルード。  
  
 ここでは、以下の内容について説明します。  
  
-   [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)  
  
-   [リソースの新規作成](../windows/how-to-create-a-resource.md)  
  
-   [リソース スクリプト ファイル内のリソースの表示](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
  
-   [テキスト形式でリソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-in-text-format.md)  
  
-   [コンパイル時のリソースのインクルード](../windows/how-to-include-resources-at-compile-time.md)  
  
-   [リソースのコピー](../windows/how-to-copy-resources.md)  
  
-   [リソース テンプレート (.rct) の使用](../windows/how-to-use-resource-templates.md)  
  
-   [リソースのインポートとエクスポート](../windows/how-to-import-and-export-resources.md)  
  
-   [編集可能なリソース ファイルの種類](../windows/editable-file-types-for-resources.md)  
  
-   [リソース編集の影響を受けるファイル](../windows/files-affected-by-resource-editing.md)  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース エディター](../windows/resource-editors.md)   
 [リソース ファイルの操作](../windows/working-with-resource-files.md)   
 [メニューとその他のリソース](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

