---
description: '詳細情報: [マネージリソース] プロパティページ'
title: '[マネージド リソース] プロパティ ページ'
ms.date: 08/28/2019
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 42816e2b4625bc5ab4620f4caafb627f55bd9cd5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190719"
---
# <a name="managed-resources-property-page"></a>[マネージド リソース] プロパティ ページ

[ **マネージリソース** ] プロパティページでは、C++/cli プログラムで .net リソースを使用するときに、マネージリソースコンパイラ [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) の次のプロパティが公開されます。

- **リソース論理名**

   生成された中間 .resources ファイルの *論理名* を指定します。 論理名は、リソースの読み込みに使用される名前です。 論理名が指定されていない場合は、リソース (.resx) ファイル名が論理名として使用されます。

- **出力ファイル名**

   リソース (.resx) ファイルによって決定する最終出力ファイルの名前を指定します。

- **既定のローカライズされたリソース**

   特定の .resx ファイルが既定のリソースまたはサテライト .dll に変更を与えるかどうかを指定します。

[ **マネージリソース** ] プロパティページにアクセスする方法の詳細については、「 [Visual Studio での C++ コンパイラとビルドプロパティの設定](../working-with-project-properties.md)」を参照してください。

## <a name="see-also"></a>関連項目

[RC の使用 (RC コマンドライン)](/windows/win32/menurc/using-rc-the-rc-command-line-)<br>
[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)<br>
[/Assemblyresource (マネージリソースの埋め込み)](assemblyresource-embed-a-managed-resource.md)
