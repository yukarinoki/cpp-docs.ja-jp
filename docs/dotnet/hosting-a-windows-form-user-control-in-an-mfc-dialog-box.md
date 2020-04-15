---
title: MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 2704e04df3792edfee6c39f597fcbe71b6ce51b4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374493"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト

MFC は、Windows フォーム コントロールを特殊な種類の ActiveX コントロールとしてホストし、ActiveX インターフェイス、およびクラスのプロパティ<xref:System.Windows.Forms.Control>とメソッドを使用してコントロールと通信します。 コントロールを操作するには、.NET Framework のプロパティとメソッドを使用することをお勧めします。

MFC で使用される Windows フォームを示すサンプル アプリケーションについては[、「MFC と Windows フォームの統合](https://www.microsoft.com/download/details.aspx?id=2113)」を参照してください。

> [!NOTE]
> 現在のリリースでは、オブジェクト`CDialogBar`は Windows フォーム コントロールをホストできません。

## <a name="in-this-section"></a>このセクションの内容

[方法: ダイアログ ボックスにユーザー コントロールおよびホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[方法 : Windows フォームを使用して DDX/DDV データ バインディングを実行する](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>リファレンス

[CWinForms コントロール クラス](../mfc/reference/cwinformscontrol-class.md)&#124; [CDialog クラス](../mfc/reference/cdialog-class.md)&#124; [CWnd クラス](../mfc/reference/cwnd-class.md)&#124;<xref:System.Windows.Forms.Control>

## <a name="see-also"></a>関連項目

[MFC での Windows フォーム ユーザー コントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows フォーム/MFC プログラミングの違い](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[WINDOWS フォーム ユーザー コントロールを MFC ダイアログ ボックスとしてホストする](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
