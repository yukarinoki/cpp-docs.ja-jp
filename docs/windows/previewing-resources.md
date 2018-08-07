---
title: リソースのプレビュー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff41dd0aad30382eb5229679054a74526652737
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605020"
---
# <a name="previewing-resources"></a>リソースのプレビュー
リソースをプレビューを開かずにグラフィカルなリソースを表示することができます。 プレビューは、リソース識別子を数値に変更されるため、コンパイルした後にも実行可能ファイルの場合に便利です。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューでそれらをすばやく識別できます。  
  
 次のリソースの種類の視覚的レイアウトをプレビューできます。  
  
-   ビットマップ  
  
-   ダイアログ  
  
-   アイコン  
  
-   メニュー  
  
-   カーソル  
  
-   ツール バー  
  
 ビジュアルのプレビュー機能は、アクセラレータ、マニフェスト、文字列テーブル、およびバージョン情報リソースには適用されません。  
  
### <a name="to-preview-resources"></a>リソースをプレビューするには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)またはドキュメント ウィンドウは、リソース、たとえば、IDD_ABOUTBOX を選択します。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、クリックして、**プロパティ ページ**ボタンをクリックします。  
  
     \- または -  
  
3.  **ビュー**  メニューのをクリックして**プロパティ ページ**します。  
  
     リソースのプロパティ ページでは、そのリソースのプレビューを表示するが開きます。 使用し、下矢印キー リソース ビュー、またはドキュメント ウィンドウのツリー コントロールを移動することができます。 プロパティ ページは開いたままにし、フォーカスがあり、プレビューを表示することは、任意のリソースを表示します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件 
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [リソース エディター](../windows/resource-editors.md)