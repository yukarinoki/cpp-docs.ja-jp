---
title: ダイアログ エディターのカスタム コントロール |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- Custom Control
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], templates
- custom controls [Visual Studio], dialog boxes
- custom controls [Visual Studio]
- dialog box controls, custom (user) controls
- Dialog editor, custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0b197baa61d741452219529e44be0e9ba1a154ce
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651052"
---
# <a name="custom-controls-in-the-dialog-editor"></a>ダイアログ エディターのカスタム コントロール
ダイアログ エディターを使用すると、既存の「カスタム」または"user"コントロールのダイアログ ボックスのテンプレート。  
  
> [!NOTE]
>  この意味でのカスタム コントロールでは、ActiveX コントロールと混同しないようにします。 ActiveX コントロールがカスタムの OLE コントロールとも呼ばれます。 また、Windows でオーナー描画コントロールでこれらのコントロールを混同しないでください。  
  
 この機能は、Windows によって提供されるもの以外のコントロールを使用することができます。 実行時に、コントロールは、ウィンドウ クラス (いないのと同じ C++ クラス) に関連付けられます。 同じタスクを実行する一般的な方法では、ダイアログ ボックスで、静的コントロールなどの任意のコントロールをインストールします。 実行時で、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)機能、そのコントロールを削除し、独自のカスタム コントロールに置き換えます。  
  
 これは、以前の技術です。 今すぐ ActiveX コントロールまたは Windows のコモン コントロールのサブクラスを作成するほとんどの場合に推奨します。  
  
 これらのカスタム コントロール用に限定されます。  
  
-   ダイアログ ボックスで、場所を設定します。  
  
-   キャプションを入力します。  
  
-   (アプリケーション コードは、コントロールをこの名前に登録する必要があります)、コントロールの Windows クラスの名前を識別します。  
  
-   コントロールのスタイルを設定する 32 ビット 16 進値を入力します。  
  
-   拡張スタイルを設定します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)