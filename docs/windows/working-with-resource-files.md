---
title: Working with Resource Files |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], about resources
- resources [C++], about resource files
- resource files, about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d96b9430cd5a6a4a9f3d65ab60c49a38b0530db7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211098"
---
# <a name="working-with-resource-files"></a>リソース ファイルの操作

> [!WARNING]
> このセクションは、C++ で記述された Windows デスクトップ アプリケーションに適用されます。 C++ で記述されたユニバーサル Windows プラットフォーム アプリでのリソースについては、次を参照してください。[アプリ リソースの定義](https://msdn.microsoft.com/476ea844-632c-4467-9ce3-966be1350dd4)します。
>
> C++ のリソースを追加する方法について/cli CLI プロジェクトを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

リソースは幅広い要素で構成できます。ユーザーに情報を提供するインターフェイス要素 (ビットマップ、アイコン、カーソルなど)、アプリケーションで必要なデータが含まれたカスタム リソース、セットアップ API によって使用されるバージョン リソース、メニューおよびダイアログ ボックス リソースなどがあります。

新しいリソースをプロジェクトに追加し、適切なリソース エディターを使用してそれらのリソースを変更できます。 ほとんどの Visual C++ ウィザードでは、プロジェクトの .rc ファイルが自動的に生成されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="in-this-section"></a>このセクションの内容

[リソース ファイル](../windows/resource-files-visual-studio.md)  
リソース ファイルと、Windows デスクトップ アプリケーションでリソース ファイルがどのように使用されるかについて説明します。 また、リソース ファイルの使用方法について説明するトピックへのリンクも示します。

[シンボル: リソース識別子](../windows/symbols-resource-identifiers.md)  
シンボルについて説明し、プロジェクトのシンボルを管理するための **[リソース シンボル]** ダイアログ ボックスの使用方法に関する情報を提供します。

[リソース エディター](../windows/resource-editors.md)  
Visual Studio で提供されるリソース エディターと各エディターで変更できるリソースの種類について説明し、各エディターの使用方法の詳細へのリンクを示します。

## <a name="related-sections"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md)  
Visual C++ のドキュメントへのリンクを示します。

[Visual Studio の概要](https://msdn.microsoft.com/99997089-56ff-4d60-81a9-447062dc98ac)  
同じ統合開発環境 (IDE: Integrated Development Environment) を使用し、混合言語ソリューションを作成するときにツールを共有し、作業を簡易化するための開発ツールの完全なセットについて説明します。

[ご意見](/visualstudio/ide/talk-to-us)  
ドキュメント セットの使用方法、製品サポートへの連絡、アクセシビリティ機能の使用に関する情報へのリンクを示します。

## <a name="see-also"></a>関連項目

[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)  
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)