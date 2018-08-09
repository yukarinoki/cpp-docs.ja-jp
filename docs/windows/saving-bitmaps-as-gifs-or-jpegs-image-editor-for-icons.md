---
title: ビットマップの保存 Gif 形式または Jpeg (アイコン用イメージ エディター) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- .gif files, saving bitmaps as
- jpg files, saving bitmaps as
- jpeg files, saving bitmaps as
- .jpg files, saving bitmaps as
- Image editor [C++], converting image formats
- gif files, saving bitmaps as
- bitmaps [C++], converting formats
- .jpeg files, saving bitmaps as
- graphics [C++], converting formats
- images [C++], converting formats
ms.assetid: 115df69f-10fb-4e6f-906b-853c1e4a54af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb2b1e8435cc53ec82ab1f957710850d7b5de3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010692"
---
# <a name="saving-bitmaps-as-gifs-or-jpegs-image-editor-for-icons"></a>GIF 形式または JPEG 形式でのビットマップの保存 (アイコン用イメージ エディター)
ビットマップを作成するときに、イメージはビットマップ (.bmp) の形式で作成されます。 ただし、他のグラフィック形式または gif 形式や JPEG としてイメージを保存することができます。  
  
> [!NOTE]
>  このプロセスは、アイコンとカーソルには適用されません。  
  
### <a name="to-create-and-save-a-bitmap-as-a-gif-or-jpeg"></a>作成し、.jpeg、.gif としてビットマップを保存するには  
  
1.  **ファイル** メニューの 選択**オープン**、 をクリックし、**ファイル**します。  
  
2.  **新しいファイル ダイアログ ボックス**、 をクリックして、 **Visual C**フォルダーを選択し、**ビットマップ ファイル (.bmp)** で、**テンプレート**ボックスし、 をクリックして**開いている**します。  
  
     ビットマップが開きます、**イメージ**エディター。  
  
3.  必要に応じて、新しいビットマップを変更を加えます。  
  
4.  ビットマップで開いたままで、**イメージ**エディター、 をクリックして**保存*ファイル名*として .bmp**上、**ファイル**メニュー。  
  
5.  **ファイルに名前を付けて** ダイアログ ボックスに、ファイルとファイル形式で目的を示す拡張機能を提供する名前を入力、**ファイル名**ボックス。 たとえば、 *myfile.gif*します。  
  
     > [!NOTE]
     > 構成データベースを作成するか、別のファイル形式として保存するには、プロジェクトの外部のビットマップを開きます。 作成するか、プロジェクト内で開いて、**付けて**コマンドは使用できません。 詳細については、次を参照してください。[を表示するリソースで、リソース スクリプト ファイル プロジェクトの外側 (スタンドアロン)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。  
  
6.  **[保存]** をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="see-also"></a>関連項目  
 [グラフィカル リソースの編集](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [アイコン用イメージ エディター](../windows/image-editor-for-icons.md)