---
title: リソースのプレビュー |Microsoft ドキュメント
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
ms.openlocfilehash: 32d0082d050ceb391a4346e2a4a38ff71c3cf2a3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="previewing-resources"></a>リソースのプレビュー
リソースをプレビューするには、グラフィカルなリソースを開かずに表示することができます。 プレビューは、リソース識別子を数値に変更されるため、コンパイルした後にも実行可能ファイルに役立ちます。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューがすばやく識別できます。  
  
 次のリソースの種類の視覚的なレイアウトをプレビューすることができます。  
  
-   ビットマップ  
  
-   ダイアログ  
  
-   アイコン  
  
-   メニュー  
  
-   カーソル  
  
-   ツール バー  
  
 視覚的なプレビュー機能は、アクセラレータ、マニフェスト、文字列テーブル、およびバージョン情報リソースには適用されません。  
  
### <a name="to-preview-resources"></a>リソースをプレビューするには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)またはドキュメントのウィンドウで、IDD_ABOUTBOX、リソースを選択します。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)をクリックして、**プロパティ ページ**ボタンをクリックします。  
  
     \- または -  
  
3.  **ビュー**  メニューのをクリックして**プロパティ ページ**です。  
  
     リソースのプロパティ ページでは、そのリソースのプレビューの表示を開きます。 上矢印を使用して、下向きの矢印キー リソース ビューまたはドキュメント ウィンドウのツリー コントロールを移動することができます。 プロパティ ページは開いたままにし、フォーカスがあり、プレビューを表示することは、任意のリソースを表示します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: プロジェクト (スタンドアロン) の外側でリソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [リソース エディター](../windows/resource-editors.md)

