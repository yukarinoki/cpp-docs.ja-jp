---
title: ActiveX コントロールのダイアログ ボックスの挿入 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.insertActiveXControls
dev_langs:
- C++
helpviewer_keywords:
- Insert ActiveX Control dialog box
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: 06638ea3-0726-40da-a989-9b89292d0e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0cf6c5efb0c7613c1332ce05483bd311b037a9b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194483"
---
# <a name="insert-activex-control-dialog-box"></a>[ActiveX コントロールの挿入] ダイアログ ボックス

このダイアログ ボックスを使用する[ダイアログ ボックスに ActiveX コントロールを挿入](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)を使用しているときに、[ダイアログ エディター](../windows/dialog-editor.md)します。

### <a name="activex-control"></a>ActiveX コントロール

Active X コントロールの一覧が表示されます。 このダイアログ ボックスからコントロールを挿入するラッパー クラスを生成しません。 ラッパー クラスを必要がある場合を使用して、[クラス ビュー](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925)を作成する (詳細については、次を参照してください。[クラスの追加](../ide/adding-a-class-visual-cpp.md))。 このダイアログ ボックスで、Active X コントロールが表示されない場合は、ベンダーの指示に従って、コントロールをインストールしてみてください。

### <a name="path"></a>パス

ActiveX コントロールが掲載されているファイルを表示します。

コントロールを配置することができます、**ツールボックス**ウィンドウを簡単にアクセスします。 詳細については、次を参照してください。[ツールボックスのカスタマイズ ダイアログ ボックス](https://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[[ダイアログ エディター] タブ ([ツールボックス])](../windows/dialog-editor-tab-toolbox.md)  
[リソース ファイル](../windows/resource-files-visual-studio.md)  
[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)