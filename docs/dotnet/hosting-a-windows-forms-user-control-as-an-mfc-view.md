---
title: MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: c041ae941858184245879ced972c19e6e998b677
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544561"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC ビューとしての Windows フォーム ユーザー コントロールのホスト

MFC では、MFC ビューでの Windows フォーム ユーザー コントロールをホストするのに CWinFormsView クラスを使用します。 MFC Windows フォーム ビューは、ActiveX コントロールです。 ユーザー コントロールがネイティブ ビューの子としてホストされているネイティブ ビューの全体のクライアント領域を占有しています。

最終的な結果がによって使用されるモデルに似ています、 [CFormView クラス](../mfc/reference/cformview-class.md)します。 豊富なフォーム ベースのビューを作成するには、Windows フォーム デザイナーとランタイムを活用できます。

MFC Windows フォーム ビューは、ActiveX コントロールであるためにがない同じ`hwnd`MFC ビューとして。 またへのポインターとして渡されることはできません、 [CView](../mfc/reference/cview-class.md)ビュー。 一般に、.NET Framework のメソッドを使用して、Windows フォーム ビューの使用と、Win32 にあまり依存しています。

Windows フォームと MFC を示すサンプル アプリケーションの場合、次を参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)します。

## <a name="in-this-section"></a>このセクションの内容

[方法: ユーザー コントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>関連項目

[MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[方法: 複合コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)