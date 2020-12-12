---
description: 詳細については、「MFC での Windows フォームユーザーコントロールの使用」を参照してください。
title: MFC での Windows フォーム ユーザー コントロールの使用
ms.date: 01/08/2018
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
ms.openlocfilehash: 61022d241faba1650d1a044ef6d3667febe34cde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319028"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC での Windows フォーム ユーザー コントロールの使用

Mfc Windows フォームサポートクラスを使用すると、mfc アプリケーション内の Windows フォームコントロールを MFC ダイアログボックスまたはビュー内の ActiveX コントロールとしてホストできます。 また、Windows フォームフォームを MFC ダイアログボックスとしてホストすることもできます。

以下のセクションでは、次の方法について説明します。

- MFC ダイアログボックスで Windows フォームコントロールをホストします。

- Windows フォームユーザーコントロールを MFC ビューとしてホストします。

- Windows フォームフォームを MFC ダイアログボックスとしてホストします。

> [!NOTE]
> MFC Windows フォーム統合は、MFC (が定義されているプロジェクト) と動的にリンクするプロジェクトでのみ機能 `_AFXDLL` します。

> [!NOTE]
> MFC Windows フォームインターフェイス DLL (mfcmifc80.dll) のプライベート (変更された) コピーを使用してアプリケーションをビルドする場合、Microsoft キーを独自のベンダキーに置き換える場合を除き、GAC にインストールすることはできません。 アセンブリの署名の詳細については、「アセンブリおよび厳密な名前のアセンブリ [を使用したプログラミング](/dotnet/framework/app-domains/programming-with-assemblies) [(アセンブリ署名) (C++/cli)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)」を参照してください。

MFC アプリケーションで Windows フォームを使用する場合は、アプリケーションと共に mfcmifc80.dll を再配布する必要があります。 詳細については、「 [MFC ライブラリの再配布](../windows/redistributing-the-mfc-library.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[MFC ダイアログボックスでの Windows フォームユーザーコントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[MFC ダイアログボックスとしての Windows フォームユーザーコントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>リファレンス

[CWinFormsControl クラス](../mfc/reference/cwinformscontrol-class.md)

[CWinFormsDialog クラス](../mfc/reference/cwinformsdialog-class.md)

[CWinFormsView クラス](../mfc/reference/cwinformsview-class.md)

[ICommandSource インターフェイス](../mfc/reference/icommandsource-interface.md)

[ICommandTarget インターフェイス](../mfc/reference/icommandtarget-interface.md)

[ICommandUI インターフェイス](../mfc/reference/icommandui-interface.md)

[IView インターフェイス](../mfc/reference/iview-interface.md)

[CommandHandler](../atl/commandhandler.md)

[DDX_ManagedControl](../mfc/reference/standard-dialog-data-exchange-routines.md#ddx_managedcontrol)

[UICheckState](../mfc/reference/uicheckstate-enumeration.md)

## <a name="related-sections"></a>関連項目

[Windows フォーム](/dotnet/framework/winforms/index)

[Windows フォームコントロール](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](../mfc/user-interface-elements-mfc.md)<br/>
[フォーム ビュー](../mfc/form-views-mfc.md)
