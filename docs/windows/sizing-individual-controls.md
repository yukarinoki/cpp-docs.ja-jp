---
title: 個々 のコントロールのサイズ変更 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20dc5eb7af4195c9861d09761da245cdd5d3217d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652215"
---
# <a name="sizing-individual-controls"></a>各コントロールのサイズ変更
コントロールのサイズを変更するのにには、サイズ変更ハンドルを使用します。 サイズ変更ハンドルにポインターを置き、ときにコントロールをサイズ変更できる方向を示すために図形を変更します。 アクティブなサイズ変更ハンドルは、solid;サイズ変更ハンドルが中空の場合は、その軸に沿ったコントロールのサイズ変更することはできません。  
  
 ガイドまたは余白、コントロールをスナップしてコントロールのサイズを変更することもできます。 または移動することによって 1 つは、制御し、ガイド スナップします。  
  
### <a name="to-size-a-control"></a>コントロールのサイズ  
  
1.  コントロールを選択します。  
  
2.  コントロールのサイズを変更するサイズ変更ハンドルをドラッグします。  
  
    -   サイズ変更ハンドルの上部と辺には、水平または垂直方向のサイズを変更します。  
  
    -   角にあるサイズ変更ハンドルは、水平および垂直の両方向のサイズを変更します。  
  
    > [!TIP]
    >  押しながら、時にコントロールの 1 つのダイアログ単位 (DLU) を変更すること、 **Shift**キーを使用して、 **→**と**↓**キー。  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>内のテキストに合わせてコントロールのサイズを自動的にする  
  
1.  選択**コンテンツ サイズ**から、**形式**メニュー。  
  
 \- または -  
  
-   コントロールを右クリックし、選択**コンテンツ サイズ**ショートカット メニューから。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)