---
title: ダイアログ エディターのカスタム コントロール |Microsoft ドキュメント
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
ms.openlocfilehash: 2c2bca249958e4d25ab5377540525da34802ac04
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880245"
---
# <a name="custom-controls-in-the-dialog-editor"></a>ダイアログ エディターのカスタム コントロール
ダイアログ エディターを使用するを使用して既存の"custom"または「ユーザー」コントロールはダイアログ ボックス テンプレートでします。  
  
> [!NOTE]
>  この意味でのカスタム コントロールでは、ActiveX コントロールと混同しないでください。 ActiveX コントロールがカスタムの OLE コントロールとも呼ばれます。 また、Windows のオーナー描画コントロールでこれらのコントロールを混同しないでください。  
  
 この機能は、Windows で指定されている以外のコントロールを使用できるようにするものです。 実行時に、コントロールは、(同じではありません、C++ クラス) ウィンドウ クラスに関連付けられます。 同じタスクを実行する一般的な方法では、ダイアログ ボックスで、静的なコントロールなど、任意のコントロールをインストールします。 実行時で、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数、そのコントロールを削除し、独自のカスタム コントロールで置き換えます。  
  
 これは、以前の技術です。 現在は、ほとんどの場合 ActiveX コントロールまたは Windows のコモン コントロールのサブクラスを作成します。  
  
 これらのカスタム コントロール用に限定されます。  
  
-   ダイアログ ボックスで、場所を設定します。  
  
-   キャプションを入力します。  
  
-   (アプリケーション コードは、コントロールをこの名前に登録する必要があります)、コントロールのウィンドウ クラスの名前を識別します。  
  
-   コントロールのスタイルを設定する 32 ビットの 16 進値を入力します。  
  
-   拡張スタイルを設定します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

