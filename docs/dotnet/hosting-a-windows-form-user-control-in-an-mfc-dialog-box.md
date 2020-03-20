---
title: MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 8925b86a5920df6a53a2625b782cf41e1a7fe32c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "79544791"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト

MFC では、特殊な種類の ActiveX コントロールとして Windows フォームコントロールをホストし、ActiveX インターフェイス、および <xref:System.Windows.Forms.Control> クラスのプロパティとメソッドを使用してコントロールと通信します。 コントロールを操作するには .NET Framework のプロパティとメソッドを使用することをお勧めします。

MFC で使用 Windows フォームを示すサンプルアプリケーションについては、「 [mfc と Windows フォームの統合](https://www.microsoft.com/download/details.aspx?id=2113)」を参照してください。

> [!NOTE]
>  現在のリリースでは、`CDialogBar` オブジェクトは Windows フォームコントロールをホストできません。

## <a name="in-this-section"></a>このセクションの内容

[方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[方法: Windows フォームで DDX/DDV データバインディングを実行する](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>参照

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog](../mfc/reference/cdialog-class.md) &#124;クラス[CWnd クラス](../mfc/reference/cwnd-class.md) &#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>参照

[MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows フォームと MFC のプログラミング上の違い](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
