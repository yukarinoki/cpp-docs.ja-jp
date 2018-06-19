---
title: MFC におけるユーザー コントロールをフォーム、Windows を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 1/08/2018
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- interoperability [C++], Windows Forms in MFC
- interoperability [C++], MFC
- interop [C++], Windows Forms in MFC
- interop [C++], MFC
- Windows Forms [C++], MFC support
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8ceb424d6c5061ac5ccafc62d8748be4de3ab3d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33174314"
---
# <a name="using-a-windows-form-user-control-in-mfc"></a>MFC での Windows フォーム ユーザー コントロールの使用

MFC Windows フォーム サポート クラスを使用して、ホストして Windows フォーム コントロール、MFC アプリケーション内で MFC ダイアログ ボックスまたはビュー内で ActiveX コントロールとして。 さらに、Windows フォームのフォームの場合は、MFC ダイアログ ボックスとしてホストされていることができます。

次のセクションで説明する方法。

- MFC ダイアログ ボックスで、Windows フォーム コントロールをホストします。

- MFC ビューとして Windows フォーム ユーザー コントロールをホストします。

- MFC ダイアログ ボックスとして、Windows フォームをホストします。

> [!NOTE]
> MFC Windows フォームの統合は MFC と動的にリンクするプロジェクトでのみ動作 (プロジェクトを`_AFXDLL`が定義されている)。

> [!NOTE]
> MFC Windows フォームのインターフェイス DLL (mfcmifc80.dll) の場合は、プライベート (変更) コピーを使用してアプリケーションをビルドするときに、Microsoft のキーを独自の仕入先キーに置き換えますを除き、GAC にインストールするには失敗します。 アセンブリの署名の詳細については、次を参照してください。[アセンブリを使用したプログラミング](/dotnet/framework/app-domains/programming-with-assemblies)と[厳密な名前のアセンブリ (アセンブリ署名) (C + + CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)です。

Windows フォームを使用するサンプル アプリケーションでは、次を参照してください[「: Windows フォームで .NET Framework リソースを示します](http://msdn.microsoft.com/ac932aed-5502-4667-be29-709bca435317)、[電卓のサンプル: Windows フォームの型の電卓](http://msdn.microsoft.com/2283b516-3b7e-45f2-80c4-fdcfb366ce25)、および。[Scribble サンプル: MDI 描画アプリケーション](http://msdn.microsoft.com/f025da3e-659b-4222-b991-554a1b8b2358)です。

MFC で使用される Windows フォームを表示するサンプル アプリケーションを参照してください。 [MFC と Windows フォーム統合](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)です。

MFC アプリケーションでは、Windows フォームを使用する場合は、アプリケーションと共に mfcmifc80.dll を再配布する必要があります。 詳細については、次を参照してください。 [MFC ライブラリの再配布](../ide/redistributing-the-mfc-library.md)です。

## <a name="in-this-section"></a>このセクションの内容

[MFC ダイアログ ボックスにおける Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

[MFC ダイアログ ボックスとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)

## <a name="reference"></a>参照

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

[Windows フォーム コントロール](/dotnet/framework/winforms/controls/index)

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)  
[フォーム ビュー](../mfc/form-views-mfc.md)  
