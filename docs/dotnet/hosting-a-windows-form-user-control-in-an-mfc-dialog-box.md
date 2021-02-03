---
description: '詳細情報: MFC ダイアログボックスでの Windows フォームユーザーコントロールのホスト'
title: MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト
ms.date: 11/04/2016
helpviewer_keywords:
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
ms.openlocfilehash: 1bd1db9d9805c10247840ca6043c94d4e3e3abe7
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522808"
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト

MFC では、特殊な種類の ActiveX コントロールとして Windows フォームコントロールをホストし、ActiveX インターフェイス、およびクラスのプロパティとメソッドを使用してコントロールと通信し <xref:System.Windows.Forms.Control> ます。 コントロールを操作するには .NET Framework のプロパティとメソッドを使用することをお勧めします。

> [!NOTE]
> 現在のリリースでは、 `CDialogBar` オブジェクトが Windows フォームコントロールをホストすることはできません。

## <a name="in-this-section"></a>このセクションの内容

[方法: ダイアログボックスにユーザーコントロールとホストを作成する](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)

[方法: Windows フォームで DDX/DDV データバインディングを実行する](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)

[方法: ネイティブ C++ クラスからの Windows フォームイベントをシンクする](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)

## <a name="reference"></a>リファレンス

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog](../mfc/reference/cdialog-class.md) クラス &#124; [CWnd クラス](../mfc/reference/cwnd-class.md) &#124; <xref:System.Windows.Forms.Control>

## <a name="see-also"></a>関連項目

[MFC での Windows フォームユーザーコントロールの使用](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
[Windows フォームと MFC のプログラミング上の違い](../dotnet/windows-forms-mfc-programming-differences.md)<br/>
[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)<br/>
[MFC ダイアログボックスとしての Windows フォームユーザーコントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
