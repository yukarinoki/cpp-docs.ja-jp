---
description: 詳細については、「MFC ビューとして Windows フォームユーザーコントロールをホストする」を参照してください。
title: MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: 4e66d4ace83e0026ec7a95cbe1b94462a163dddf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164641"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC ビューとしての Windows フォーム ユーザー コントロールのホスト

MFC では、CWinFormsView クラスを使用して、MFC ビューで Windows フォームユーザーコントロールをホストします。 MFC Windows フォームビューは ActiveX コントロールです。 ユーザーコントロールは、ネイティブビューの子としてホストされ、ネイティブビューのクライアント領域全体を占有します。

最終的な結果は、 [CFormView クラス](../mfc/reference/cformview-class.md)によって使用されるモデルに似ています。 これにより、Windows フォームデザイナーとランタイムを利用して、豊富なフォームベースのビューを作成できます。

MFC Windows フォームビューは ActiveX コントロールであるため、MFC ビューと同じではありません `hwnd` 。 また、 [CView](../mfc/reference/cview-class.md) ビューへのポインターとして渡すこともできません。 一般に、.NET Framework メソッドを使用して Windows フォームビューを操作し、Win32 に依存しないようにします。

MFC で使用 Windows フォームを示すサンプルアプリケーションについては、「 [mfc と Windows フォームの統合](https://www.microsoft.com/download/details.aspx?id=2113)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[方法: ユーザーコントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[方法: Windows フォームコントロールにコマンドルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[方法: Windows フォームコントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>関連項目

[MFC での Windows フォームユーザーコントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[方法: 複合コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
