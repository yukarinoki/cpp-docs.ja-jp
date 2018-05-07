---
title: ユーザー コントロールを MFC ビューとして Windows をホストしているフォーム |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf9e54b3e2808a232bc13052c885a341cb51297f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
MFC では、CWinFormsView クラスを使用して、Windows フォーム ユーザー コントロールを MFC ビューでホストします。 MFC Windows フォーム ビューは、ActiveX コントロールです。 ユーザー コントロールは、ネイティブのビューの子としてホストされ、ネイティブ ビューの全体のクライアント領域を占有します。  
  
 最終的な結果がによって使用されるモデルに似ています、 [CFormView クラス](../mfc/reference/cformview-class.md)です。 これは、操作により、機能豊富なフォーム ベースのビューを作成するには、Windows フォーム デザイナーとランタイムを活用できます。  
  
 MFC Windows フォーム ビューが ActiveX コントロールであるためがない同じ`hwnd`MFC ビューとして。 またへのポインターとして渡されることはできません、 [CView](../mfc/reference/cview-class.md)ビュー。 一般に、Windows フォーム ビューの操作を使用して Win32 にはそれほどに .NET Framework のメソッドを使用します。  
  
 MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC における Windows フォーム ユーザー コントロールを使用します。](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [方法: 複合コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)