---
title: ダイアログ エディター (C++) のカスタム コントロール
ms.date: 11/04/2016
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: f494b314-4000-4bbe-bbd0-4b18fb71ede1
ms.openlocfilehash: c48ad87948037fa843fdc16a016ae23bf139feb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677098"
---
# <a name="custom-controls-in-the-dialog-editor-c"></a>ダイアログ エディター (C++) のカスタム コントロール

ダイアログ エディターを使用すると、既存の「カスタム」または"user"コントロールのダイアログ ボックスのテンプレート。

> [!NOTE]
> この意味でのカスタム コントロールでは、ActiveX コントロールと混同しないようにします。 ActiveX コントロールがカスタムの OLE コントロールとも呼ばれます。 また、Windows でオーナー描画コントロールでこれらのコントロールを混同しないでください。

この機能は、Windows によって提供されるもの以外のコントロールを使用することができます。 実行時に、コントロールは、ウィンドウ クラス (いないのと同じ C++ クラス) に関連付けられます。 同じタスクを実行する一般的な方法では、ダイアログ ボックスで、静的コントロールなどの任意のコントロールをインストールします。 実行時で、 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)機能、そのコントロールを削除し、独自のカスタム コントロールに置き換えます。

これは、以前の技術です。 今すぐ ActiveX コントロールまたは Windows のコモン コントロールのサブクラスを作成するほとんどの場合に推奨します。

これらのカスタム コントロール用に限定されます。

- ダイアログ ボックスで、場所を設定します。

- キャプションを入力します。

- (アプリケーション コードは、コントロールをこの名前に登録する必要があります)、コントロールの Windows クラスの名前を識別します。

- コントロールのスタイルを設定する 32 ビット 16 進値を入力します。

- 拡張スタイルを設定します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)