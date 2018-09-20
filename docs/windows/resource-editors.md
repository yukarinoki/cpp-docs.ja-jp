---
title: リソース エディター (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
dev_langs:
- C++
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b9b9666e9c20e955d8f3705ebd93e7c890d2bc0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391924"
---
# <a name="resource-editors"></a>リソース エディター

A**リソース**エディターは、専用の環境の作成または Visual Studio プロジェクトに含まれているリソースを変更します。 Visual Studio のリソース エディターでは、アプリケーションのリソースをすばやく簡単に作成して変更できるようにする技術とインターフェイスを共有します。 リソース エディターを使用すると、 [リソースを適切なエディターで表示して編集](../windows/viewing-and-editing-resources-in-a-resource-editor.md) でき、 [リソースをプレビュー](../windows/previewing-resources.md)することができます。

リソースを作成したり開いたりすると、適切なエディターが自動的に開きます。

**注** マネージド プロジェクトでは、リソース スクリプト ファイルは使用しないため、 **ソリューション エクスプローラー**からリソースを開く必要があります。 [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージド プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージド リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

|使用|編集|
|----------------|----------------|
|[アクセラレータ エディター](../windows/accelerator-editor.md)|アクセラレータ テーブル (Visual C++ プロジェクトでの)|
|[Binary Editor](binary-editor.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのバイナリ データの情報およびカスタム リソース。|
|[ダイアログ エディター](../windows/dialog-editor.md)|ダイアログ ボックス (Visual C++ プロジェクトでの)|
|[Image Editor](../windows/image-editor-for-icons.md)|Visual C++、Visual Basic、または Visual C# プロジェクトのビットマップ、アイコン、カーソル、およびその他のイメージ ファイル。|
|[メニュー エディター](../windows/menu-editor.md)|Visual C++ プロジェクトのメニュー リソース。|
|[Ribbon エディター](../mfc/ribbon-designer-mfc.md)|MFC プロジェクトのリボン リソース。|
|[ストリング エディター](../windows/string-editor.md)|文字列テーブル (Visual C++ プロジェクトでの)|
|[ツール バー エディター](../windows/toolbar-editor.md)|Visual C++ プロジェクトのツール バー リソース。 ツール バー エディターは、イメージ エディターの一部です。|
|[バージョン エディター](../windows/version-information-editor.md)|Visual C++ プロジェクトのバージョン情報です。|

## <a name="requirements"></a>要件

なし

## <a name="see-also"></a>関連項目

[リソース ファイルの操作](../windows/working-with-resource-files.md)<br/>
[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)