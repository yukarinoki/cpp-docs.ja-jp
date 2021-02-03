---
description: 詳細については、「MFC ビューとして Windows フォームユーザーコントロールをホストする」を参照してください。
title: MFC ビューとしての Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms controls [C++], hosting as an MFC view
- hosting Windows Forms control [C++]
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
ms.openlocfilehash: b9f0eba7f052bee6c2cba89b7a5c22bcb1604cc3
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522795"
---
# <a name="hosting-a-windows-forms-user-control-as-an-mfc-view"></a>MFC ビューとしての Windows フォーム ユーザー コントロールのホスト

MFC では、CWinFormsView クラスを使用して、MFC ビューで Windows フォームユーザーコントロールをホストします。 MFC Windows フォームビューは ActiveX コントロールです。 ユーザーコントロールは、ネイティブビューの子としてホストされ、ネイティブビューのクライアント領域全体を占有します。

最終的な結果は、 [CFormView クラス](../mfc/reference/cformview-class.md)によって使用されるモデルに似ています。 これにより、Windows フォームデザイナーとランタイムを利用して、豊富なフォームベースのビューを作成できます。

MFC Windows フォームビューは ActiveX コントロールであるため、MFC ビューと同じではありません `hwnd` 。 また、 [CView](../mfc/reference/cview-class.md) ビューへのポインターとして渡すこともできません。 一般に、.NET Framework メソッドを使用して Windows フォームビューを操作し、Win32 に依存しないようにします。

## <a name="in-this-section"></a>このセクションの内容

[方法: ユーザーコントロールを作成し、MDI ビューをホストする](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)

[方法: Windows フォームコントロールにコマンドルーティングを追加する](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)

[方法: Windows フォームコントロールのプロパティとメソッドを呼び出す](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)

## <a name="see-also"></a>関連項目

[MFC での Windows フォームユーザーコントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[方法: 複合コントロールを作成する](/dotnet/framework/winforms/controls/how-to-author-composite-controls)
