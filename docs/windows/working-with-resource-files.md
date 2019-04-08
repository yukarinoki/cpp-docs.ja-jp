---
title: Working with Resource Files (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: a08c7ecb153b790f06da386ac93d1f05f5981e61
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037738"
---
# <a name="working-with-resource-files"></a>リソース ファイルの操作

> [!WARNING]
> このセクションは、C++ で記述された Windows デスクトップ アプリケーションに適用されます。
>
> C++ で記述されたユニバーサル Windows プラットフォーム アプリでのリソースについては、次を参照してください[アプリ リソースの定義](/windows/uwp/app-resources/)、c++ のリソースを追加する方法または/cli CLI (マネージ) プロジェクトでは、を参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で.NET Framework 開発者ガイド。

リソースなどのさまざまな要素で構成できます。

- ビットマップ、アイコン、カーソルなどのユーザーに情報を提供するインターフェイスの要素。
- カスタム リソース データとアプリケーションが含まれている必要があります。
- によって使用されているバージョンのリソースは、Api をセットアップします。
- メニューおよびダイアログ ボックスのリソース。

新しいリソースをプロジェクトに追加し、適切なリソース エディターを使用してそれらのリソースを変更できます。 ほとんどの Visual C++ ウィザードでは、プロジェクトの .rc ファイルが自動的に生成されます。

> [!NOTE]
> **リソース エディター**と**リソース ビュー** Express エディションでは使用できません。

マネージ プロジェクトにリソース ファイルを手動で追加するには、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 この記事には、リソースへのアクセス、静的なリソースを表示およびリソース文字列をプロパティに割り当てる方法が含まれています。

グローバル化を管理対象アプリでリソースをローカライズは、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="in-this-section"></a>このセクションの内容

[リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)<br/>
リソース ファイルと Windows デスクトップ アプリケーションでの使用方法について説明します。 リソース ファイルを使用する方法について説明する記事へのリンクもあります。

[リソース識別子 (シンボル)](../windows/symbols-resource-identifiers.md)<br/>
シンボルについて説明し、プロジェクトのシンボルを管理するための **[リソース シンボル]** ダイアログ ボックスの使用方法に関する情報を提供します。

[リソース エディター](../windows/resource-editors.md)<br/>
Visual Studio と各エディターを使用して変更できるリソースの種類で提供されるリソース エディターについて説明します。 各エディターの使用に関する詳細情報へのリンクを提供します。

## <a name="related-sections"></a>関連項目

[Visual C++](../overview/visual-cpp-in-visual-studio.md)<br/>
Visual C++ のドキュメントへのリンクを示します。

[Talk to Us](/visualstudio/ide/talk-to-us)<br/>
ドキュメント セットの使用方法、製品サポートへの連絡、アクセシビリティ機能の使用に関する情報へのリンクを示します。

## <a name="see-also"></a>関連項目

[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)<br/>
[メニューとその他のリソース](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)