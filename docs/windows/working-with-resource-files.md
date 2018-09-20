---
title: Working with Resource Files (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d72e37b8625480779620025dfd1e1eda1101b824
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430554"
---
# <a name="working-with-resource-files"></a>リソース ファイルの操作

> [!WARNING]
> このセクションは、C++ で記述された Windows デスクトップ アプリケーションに適用されます。 C++ で記述されたユニバーサル Windows プラットフォーム アプリでのリソースについては、次を参照してください。[アプリ リソースの定義](/windows/uwp/app-resources/)します。
>
> C++ のリソースを追加する方法について/cli CLI プロジェクトを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

リソースは幅広い要素で構成できます。ユーザーに情報を提供するインターフェイス要素 (ビットマップ、アイコン、カーソルなど)、アプリケーションで必要なデータが含まれたカスタム リソース、セットアップ API によって使用されるバージョン リソース、メニューおよびダイアログ ボックス リソースなどがあります。

新しいリソースをプロジェクトに追加し、適切なリソース エディターを使用してそれらのリソースを変更できます。 ほとんどの Visual C++ ウィザードでは、プロジェクトの .rc ファイルが自動的に生成されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="in-this-section"></a>このセクションの内容

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
リソース ファイルと、Windows デスクトップ アプリケーションでリソース ファイルがどのように使用されるかについて説明します。 また、リソース ファイルの使用方法について説明するトピックへのリンクも示します。

[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)<br/>
シンボルについて説明し、プロジェクトのシンボルを管理するための **[リソース シンボル]** ダイアログ ボックスの使用方法に関する情報を提供します。

[リソース エディター](../windows/resource-editors.md)<br/>
Visual Studio で提供されるリソース エディターと各エディターで変更できるリソースの種類について説明し、各エディターの使用方法の詳細へのリンクを示します。

## <a name="related-sections"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md)<br/>
Visual C++ のドキュメントへのリンクを示します。

[ご意見](/visualstudio/ide/talk-to-us)<br/>
ドキュメント セットの使用方法、製品サポートへの連絡、アクセシビリティ機能の使用に関する情報へのリンクを示します。

## <a name="see-also"></a>関連項目

[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)