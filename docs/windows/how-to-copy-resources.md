---
title: '方法: リソースをコピー |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b173be24e9f177a3156f740fcb07240c30fec75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-copy-resources"></a>方法: リソースをコピーする
それらを変更することがなく別の 1 つのファイルからのリソースをコピーすることがでくこともできます[コピー中に、言語またはリソースの条件を変更する](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md)です。  
  
 現在のリソース ファイルに、既存のリソースまたは実行可能ファイルからリソースを簡単にコピーすることができます。 これを行うには、同時にリソースが含まれる両方のファイルを開くと別に 1 つのファイルから項目をドラッグまたはコピーして貼り付ける 2 つのファイルです。 このメソッドは、リソース スクリプト (.rc) ファイルとリソース テンプレート (.rct) ファイル、および実行可能 (.exe) ファイルに対して機能します。  
  
> [!NOTE]
>  Visual C には、独自のアプリケーションで使用できるサンプル リソース ファイルが含まれています。 詳細については、次を参照してください。[クリップアート: 共通リソース](http://msdn.microsoft.com/en-us/9bac2891-b6b3-49ec-a287-cec850c707e0)です。  
  
 開いている .rc ファイル間でドラッグ アンド ドロップ メソッドを使用することができます[プロジェクト外部の](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)します。  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ メソッドを使用してファイル間でリソースをコピーするには  
  
1.  スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイル プロジェクトの外側に表示するリソース](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と Source2.rc を開きます。  
  
2.  最初の .rc ファイル内には、コピーするリソースをクリックします。 たとえば、Source1.rc、IDD_DIALOG1 をクリックします。  
  
3.  CTRL キーを押しながらし、2 番目の .rc ファイルにリソースをドラッグします。 たとえば、Source1.rc から IDD_DIALOG1 を Source2.rc にドラッグします。  
  
    > [!NOTE]
    >  CTRL キーを保持することがなくリソースをドラッグすると、コピーするのではなく、リソースが移動します。  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>コピーを使用してリソースをコピーして貼り付ける  
  
1.  スタンドアロン両方のリソース ファイルを開きます (詳細については、次を参照してください。 [、.rc ファイル プロジェクトの外側に表示するリソース](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md))。 たとえば、Source1.rc と Source2.rc です。  
  
2.  リソース (たとえば、Source1.rc) をコピーするソース ファイルでリソースを右クリックして選択**コピー**ショートカット メニューからです。  
  
3.  これにするには、リソース (たとえば、Source2.rc) を貼り付け、リソース ファイルを右クリックします。 選択**貼り付け**ショートカット メニューからです。  
  
    > [!NOTE]
    >  できませんをドラッグし、ドロップ、コピー、切り取り、または貼り付けるプロジェクト ([リソース] ビュー) でリソース ファイルと (開いているドキュメント ウィンドウで) スタンドアロンの .rc ファイル間でします。 製品の以前のバージョンで、これを行う可能性があります。  
  
    > [!NOTE]
    >  シンボル名や、既存のファイル内の値との競合を避けるためには、Visual C は変更転送されるリソースのシンボル値またはシンボル名と値を新しいファイルにコピーするときにできます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: プロジェクト (スタンドアロン) の外側でリソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)