---
title: イメージ (アイコン用イメージ エディター) のテキストのフォントを変更する |Microsoft ドキュメント
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
ms.openlocfilehash: b3ddef7e52866d5e25c3b9f5e5c580062f73e1b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>イメージのテキストのフォントの変更 (アイコン用イメージ エディター)
次の手順は、する方法の例です。  
  
-   Windows アプリケーションのアイコンにテキストを追加します。  
  
-   テキストのフォントを操作します。  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>イメージのテキストのフォントを変更するには  
  
1.  C++ Windows フォーム アプリケーションを作成します。 詳細については、「 [Windows アプリケーション プロジェクトを作成する](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)です。 [Windows フォーム アプリケーション テンプレート](http://msdn.microsoft.com/en-us/1babdebf-ab3f-4a64-a608-98499a5b9cea)既定では、プロジェクトに app.ico をという名前のファイルを追加します。  
  
2.  ソリューション エクスプ ローラーで、app.ico ファイルをダブルクリックします。 [イメージ エディター](../windows/image-editor-for-icons.md)が開きます。  
  
3.  **イメージ**メニューの **ツール**し、**テキスト ツール**です。 [テキスト ツール ダイアログ ボックス](../windows/text-tool-dialog-box-image-editor-for-icons.md)が表示されます。  
  
4.  [テキスト ツール] ダイアログ ボックスで次のように入力します。`C++`空のテキスト領域にします。 App.ico、イメージ エディターでの左上隅にあるサイズ変更可能なボックスに、このテキストが表示されます。  
  
5.  イメージ エディターでは、テキストの読みやすさを向上させるために、app.ico の中央にサイズ変更可能なボックスをドラッグします。  
  
6.  [テキスト ツール] ダイアログ ボックスでをクリックして、**フォント**ボタンをクリックします。 [テキスト ツール フォント ダイアログ ボックス](../windows/text-tool-font-dialog-box-image-editor-for-icons.md)が表示されます。  
  
7.  テキスト ツール フォント ダイアログ ボックスで選択**Times New Roman**に記載されている使用可能なフォントの一覧から、**フォント**ボックスの一覧です。  
  
8.  選択**太字**にリストされている使用可能なフォント スタイルの一覧から、**フォント スタイル**ボックスの一覧です。  
  
9. 選択**10**ポイントに表示されているサイズの使用可能な一覧から、**サイズ**ボックスの一覧です。  
  
10. クリックして、 **OK**ボタンをクリックします。 テキスト ツール フォント ダイアログ ボックスは終了し、新しいフォント設定は、テキストに適用されます。  
  
11. クリックして、**閉じる**ボタンのテキスト ツール ダイアログ ボックスをクリックします。 テキストを囲むサイズ変更可能なボックスには、イメージ エディターでは表示されません。  
  
## <a name="see-also"></a>関連項目  
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [ツール バー](../windows/toolbar-image-editor-for-icons.md)

