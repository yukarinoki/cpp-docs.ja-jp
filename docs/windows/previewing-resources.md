---
title: リソース (C++) のプレビュー
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- resources [C++], viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
ms.openlocfilehash: 79756bd71dfc731b78b21bd4df311e4848beb899
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589550"
---
# <a name="previewing-resources"></a>リソースのプレビュー

リソースをプレビューを開かずにグラフィカルなリソースを表示することができます。 プレビューは、リソース識別子を数値に変更されるため、コンパイルした後にも実行可能ファイルの場合に便利です。 多くの場合、これらの数値識別子は、十分な情報を提供しない、ため、リソースのプレビューでそれらをすばやく識別できます。

次のリソースの種類の視覚的レイアウトをプレビューできます。

- ビットマップ

- ダイアログ

- アイコン

- メニュー

- カーソル

- ツール バー

ビジュアルのプレビュー機能は、アクセラレータ、マニフェスト、文字列テーブル、およびバージョン情報リソースには適用されません。

### <a name="to-preview-resources"></a>リソースをプレビューするには

1. [リソース ビュー](../windows/resource-view-window.md)または、リソースを選択して、ドキュメント ウィンドウ**IDD_ABOUTBOX**します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、クリックして、**プロパティ ページ**ボタンをクリックします。

   \- または -

3. **ビュー**  メニューのをクリックして**プロパティ ページ**します。

   **プロパティ ページ**リソースが開き、リソースのプレビューを表示します。 使用することができますし、**を**と**ダウン**ツリーを移動する方向キーを制御**リソース ビュー**またはドキュメント ウィンドウ。 **プロパティ ページ**は開いたままにし、フォーカスがあり、プレビューを表示することは、任意のリソースを表示します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[方法: プロジェクトの外側で (スタンドアロンで) リソース スクリプト ファイルを開く](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[リソース エディター](../windows/resource-editors.md)