---
title: 挿入 ActiveX コントロール ダイアログ ボックス (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Insert ActiveX Control dialog box [C++]
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
ms.openlocfilehash: 495245141b62850067196c81bfe4c6f984dcfa88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592752"
---
# <a name="insert-activex-control-dialog-box-c"></a>挿入 ActiveX コントロール ダイアログ ボックス (C++)

このダイアログ ボックスを使用する[ダイアログ ボックスに ActiveX コントロールを挿入](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)を使用しているときに、[ダイアログ エディター](../windows/dialog-editor.md)します。

### <a name="activex-control"></a>ActiveX コントロール

Active X コントロールの一覧が表示されます。 このダイアログ ボックスからコントロールを挿入するラッパー クラスを生成しません。 ラッパー クラスを必要がある場合を使用して、[クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)を作成する (詳細については、次を参照してください。[クラスの追加](../ide/adding-a-class-visual-cpp.md))。 このダイアログ ボックスで、Active X コントロールが表示されない場合は、ベンダーの指示に従って、コントロールをインストールしてみてください。

### <a name="path"></a>パス

ActiveX コントロールが掲載されているファイルを表示します。

コントロールを配置することができます、**ツールボックス**ウィンドウを簡単にアクセスします。 詳細については、「[ツールボックス](/visualstudio/ide/reference/)」をご覧ください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[[ダイアログ エディター] タブ ([ツールボックス])](../windows/dialog-editor-tab-toolbox.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)