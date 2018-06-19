---
title: 水平スクロール バーの幅の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- list controls, scroll bar width
- CListBox::SetHorizontalExtent
- controls [C++], scroll bar
- scroll bars, displaying in controls
- horizontal scroll bar width
- CListBox class, scroll bar width
- scroll bars, width
ms.assetid: 51dad141-aa0b-46a3-a82c-46b80d603d94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34545a01c01146992c7d88ecabec1a29a7b438f2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892795"
---
# <a name="setting-the-width-of-a-horizontal-scroll-bar"></a>水平スクロール バーの幅の設定
MFC クラスを使用してダイアログ ボックスに水平スクロール バーをリスト ボックスを追加すると、スクロール バーは、アプリケーションでは自動的に表示されません。  
  
### <a name="to-make-the-scroll-bar-appear"></a>スクロール バーを表示する  
  
1.  呼び出して最も幅の広い要素の最大の幅を設定[CListBox::SetHorizontalExtent](../mfc/reference/clistbox-class.md#sethorizontalextent)コードにします。  
  
     この値を設定せず、スクロール バーは表示されません、でも、リスト ボックス内の項目は、ボックスよりも太くなってとき。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 MFC  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

