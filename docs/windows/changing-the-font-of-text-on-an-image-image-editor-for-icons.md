---
title: イメージ (アイコン用イメージ エディター) のテキストのフォントを変更する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a180a8923dd5a9e8cb257b12ee0d2ba09df8ed5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642995"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>イメージのテキストのフォントの変更 (アイコン用イメージ エディター)
次の手順では、する方法の例を示します。  
  
-   Windows アプリケーションのアイコンにテキストを追加します。  
  
-   テキストのフォントを操作します。  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>イメージのテキストのフォントを変更するには  
  
1.  C++ Windows フォーム アプリケーションを作成します。 詳細については、次を参照してください。 [Windows アプリケーション プロジェクトを作成する](http://msdn.microsoft.com/b2f93fed-c635-4705-8d0e-cf079a264efa)します。 [Windows フォーム アプリケーション テンプレート](http://msdn.microsoft.com/1babdebf-ab3f-4a64-a608-98499a5b9cea)という名前のファイルを追加します。`app.ico`既定では、プロジェクトにします。  
  
2.  **ソリューション エクスプ ローラー**、app.ico ファイルをダブルクリックします。 [イメージ エディター](../windows/image-editor-for-icons.md)が開きます。  
  
3.  **イメージ**メニューの **ツール**選び**テキスト ツール**します。 [テキスト ツール ダイアログ ボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)が表示されます。  
  
4.  **テキスト ツール**ダイアログ ボックスに「`C++`空のテキスト領域にします。 このテキストの左上隅にあるサイズ変更可能なボックスに表示されます`app.ico`の**イメージ エディター**します。  
  
5.  **イメージ エディター**、サイズ変更可能なボックス、テキストの読みやすさを向上させるために、app.ico の中央にドラッグします。  
  
6.  **テキスト ツール**ダイアログ ボックスで、をクリックして、**フォント**ボタンをクリックします。 [テキスト ツール フォント ダイアログ ボックス](../windows/text-tool-font-dialog-box-image-editor-for-icons.md)が表示されます。  
  
7.  **テキスト ツール フォント**ダイアログ ボックスで、 **Times New Roman**記載されている利用可能なフォントの一覧から、**フォント**ボックスの一覧。  
  
8.  選択**太字**でリストされている利用可能なフォント スタイルの一覧から、**フォント スタイル**ボックスの一覧。  
  
9. 選択**10**ポイントで示されたサイズの使用可能な一覧から、**サイズ**ボックスの一覧。  
  
10. をクリックして、 **OK**ボタンをクリックします。 **テキスト ツール フォント** ダイアログ ボックスが閉じ、新しいフォントの設定は、テキストに適用されます。  
  
11. をクリックして、**閉じる**のボタンでは、**テキスト ツール** ダイアログ ボックス。 サイズ変更可能なテキストを囲むボックスから消え、**イメージ エディター**します。  
  
## <a name="see-also"></a>関連項目  
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [ツール バー](../windows/toolbar-image-editor-for-icons.md)